
---
title: "WebAclAssociation"
title_tag: "aws.wafv2.WebAclAssociation"
meta_desc: "Documentation for the aws.wafv2.WebAclAssociation resource with examples, input properties, output properties, lookup functions, and supporting types."
layout: api
no_edit_this_page: true
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Creates a WAFv2 Web ACL Association.

> **NOTE on associating a WAFv2 Web ACL with a Cloudfront distribution:** Do not use this resource to associate a WAFv2 Web ACL with a Cloudfront Distribution. The [AWS API call backing this resource](https://docs.aws.amazon.com/waf/latest/APIReference/API_AssociateWebACL.html) notes that you should use the [`web_acl_id`][2] property on the [`cloudfront_distribution`][2] instead.

[1]: https://docs.aws.amazon.com/waf/latest/APIReference/API_AssociateWebACL.html
[2]: https://www.terraform.io/docs/providers/aws/r/cloudfront_distribution.html#web_acl_id

{{% examples %}}

## Example Usage

{{< chooser language "typescript,python,go,csharp" / >}}





{{< example csharp >}}

```csharp
using System.Collections.Generic;
using System.Security.Cryptography;
using System.Text;
using System.Text.Json;
using Pulumi;
using Aws = Pulumi.Aws;

class MyStack : Stack
{
	private static string ComputeSHA1(string input) {
		return BitConverter.ToString(
			SHA1.Create().ComputeHash(Encoding.UTF8.GetBytes(input))
		).Replace("-","").ToLowerInvariant());
	}

    public MyStack()
    {
        var exampleRestApi = new Aws.ApiGateway.RestApi("exampleRestApi", new Aws.ApiGateway.RestApiArgs
        {
            Body = JsonSerializer.Serialize(new Dictionary<string, object?>
            {
                { "openapi", "3.0.1" },
                { "info", new Dictionary<string, object?>
                {
                    { "title", "example" },
                    { "version", "1.0" },
                } },
                { "paths", new Dictionary<string, object?>
                {
                    { "/path1", new Dictionary<string, object?>
                    {
                        { "get", new Dictionary<string, object?>
                        {
                            { "x-amazon-apigateway-integration", new Dictionary<string, object?>
                            {
                                { "httpMethod", "GET" },
                                { "payloadFormatVersion", "1.0" },
                                { "type", "HTTP_PROXY" },
                                { "uri", "https://ip-ranges.amazonaws.com/ip-ranges.json" },
                            } },
                        } },
                    } },
                } },
            }),
        });
        var exampleDeployment = new Aws.ApiGateway.Deployment("exampleDeployment", new Aws.ApiGateway.DeploymentArgs
        {
            RestApi = exampleRestApi.Id,
            Triggers = 
            {
                { "redeployment", exampleRestApi.Body.Apply(body => JsonSerializer.Serialize(body)).Apply(toJSON => ComputeSHA1(toJSON)) },
            },
        });
        var exampleStage = new Aws.ApiGateway.Stage("exampleStage", new Aws.ApiGateway.StageArgs
        {
            Deployment = exampleDeployment.Id,
            RestApi = exampleRestApi.Id,
            StageName = "example",
        });
        var exampleWebAcl = new Aws.WafV2.WebAcl("exampleWebAcl", new Aws.WafV2.WebAclArgs
        {
            Scope = "REGIONAL",
            DefaultAction = new Aws.WafV2.Inputs.WebAclDefaultActionArgs
            {
                Allow = ,
            },
            VisibilityConfig = new Aws.WafV2.Inputs.WebAclVisibilityConfigArgs
            {
                CloudwatchMetricsEnabled = false,
                MetricName = "friendly-metric-name",
                SampledRequestsEnabled = false,
            },
        });
        var exampleWebAclAssociation = new Aws.WafV2.WebAclAssociation("exampleWebAclAssociation", new Aws.WafV2.WebAclAssociationArgs
        {
            ResourceArn = exampleStage.Arn,
            WebAclArn = exampleWebAcl.Arn,
        });
    }

}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"crypto/sha1"
	"encoding/json"
	"fmt"

	"github.com/pulumi/pulumi-aws/sdk/v4/go/aws/apigateway"
	"github.com/pulumi/pulumi-aws/sdk/v4/go/aws/wafv2"
	"github.com/pulumi/pulumi/sdk/v3/go/pulumi"
)

func sha1Hash(input string) string {
	hash := sha1.Sum([]byte(input))
	return hex.EncodeToString(hash[:])
}

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		tmpJSON0, err := json.Marshal(map[string]interface{}{
			"openapi": "3.0.1",
			"info": map[string]interface{}{
				"title":   "example",
				"version": "1.0",
			},
			"paths": map[string]interface{}{
				"/path1": map[string]interface{}{
					"get": map[string]interface{}{
						"x-amazon-apigateway-integration": map[string]interface{}{
							"httpMethod":           "GET",
							"payloadFormatVersion": "1.0",
							"type":                 "HTTP_PROXY",
							"uri":                  "https://ip-ranges.amazonaws.com/ip-ranges.json",
						},
					},
				},
			},
		})
		if err != nil {
			return err
		}
		json0 := string(tmpJSON0)
		exampleRestApi, err := apigateway.NewRestApi(ctx, "exampleRestApi", &apigateway.RestApiArgs{
			Body: pulumi.String(json0),
		})
		if err != nil {
			return err
		}
		exampleDeployment, err := apigateway.NewDeployment(ctx, "exampleDeployment", &apigateway.DeploymentArgs{
			RestApi: exampleRestApi.ID(),
			Triggers: pulumi.StringMap{
				"redeployment": exampleRestApi.Body.ApplyT(func(body string) (pulumi.String, error) {
					var _zero pulumi.String
					tmpJSON1, err := json.Marshal(body)
					if err != nil {
						return _zero, err
					}
					json1 := string(tmpJSON1)
					return json1, nil
				}).(pulumi.StringOutput).ApplyT(func(toJSON string) (pulumi.String, error) {
					return sha1Hash(toJSON), nil
				}).(pulumi.StringOutput),
			},
		})
		if err != nil {
			return err
		}
		exampleStage, err := apigateway.NewStage(ctx, "exampleStage", &apigateway.StageArgs{
			Deployment: exampleDeployment.ID(),
			RestApi:    exampleRestApi.ID(),
			StageName:  pulumi.String("example"),
		})
		if err != nil {
			return err
		}
		exampleWebAcl, err := wafv2.NewWebAcl(ctx, "exampleWebAcl", &wafv2.WebAclArgs{
			Scope: pulumi.String("REGIONAL"),
			DefaultAction: &wafv2.WebAclDefaultActionArgs{
				Allow: nil,
			},
			VisibilityConfig: &wafv2.WebAclVisibilityConfigArgs{
				CloudwatchMetricsEnabled: pulumi.Bool(false),
				MetricName:               pulumi.String("friendly-metric-name"),
				SampledRequestsEnabled:   pulumi.Bool(false),
			},
		})
		if err != nil {
			return err
		}
		_, err = wafv2.NewWebAclAssociation(ctx, "exampleWebAclAssociation", &wafv2.WebAclAssociationArgs{
			ResourceArn: exampleStage.Arn,
			WebAclArn:   exampleWebAcl.Arn,
		})
		if err != nil {
			return err
		}
		return nil
	})
}
```


{{< /example >}}


{{< example python >}}

```python
import pulumi
import hashlib
import json
import pulumi_aws as aws

example_rest_api = aws.apigateway.RestApi("exampleRestApi", body=json.dumps({
    "openapi": "3.0.1",
    "info": {
        "title": "example",
        "version": "1.0",
    },
    "paths": {
        "/path1": {
            "get": {
                "x-amazon-apigateway-integration": {
                    "httpMethod": "GET",
                    "payloadFormatVersion": "1.0",
                    "type": "HTTP_PROXY",
                    "uri": "https://ip-ranges.amazonaws.com/ip-ranges.json",
                },
            },
        },
    },
}))
example_deployment = aws.apigateway.Deployment("exampleDeployment",
    rest_api=example_rest_api.id,
    triggers={
        "redeployment": example_rest_api.body.apply(lambda body: json.dumps(body)).apply(lambda to_json: hashlib.sha1(to_json.encode()).hexdigest()),
    })
example_stage = aws.apigateway.Stage("exampleStage",
    deployment=example_deployment.id,
    rest_api=example_rest_api.id,
    stage_name="example")
example_web_acl = aws.wafv2.WebAcl("exampleWebAcl",
    scope="REGIONAL",
    default_action=aws.wafv2.WebAclDefaultActionArgs(
        allow=aws.wafv2.WebAclDefaultActionAllowArgs(),
    ),
    visibility_config=aws.wafv2.WebAclVisibilityConfigArgs(
        cloudwatch_metrics_enabled=False,
        metric_name="friendly-metric-name",
        sampled_requests_enabled=False,
    ))
example_web_acl_association = aws.wafv2.WebAclAssociation("exampleWebAclAssociation",
    resource_arn=example_stage.arn,
    web_acl_arn=example_web_acl.arn)
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";
import * as crypto from "crypto";

const exampleRestApi = new aws.apigateway.RestApi("exampleRestApi", {body: JSON.stringify({
    openapi: "3.0.1",
    info: {
        title: "example",
        version: "1.0",
    },
    paths: {
        "/path1": {
            get: {
                "x-amazon-apigateway-integration": {
                    httpMethod: "GET",
                    payloadFormatVersion: "1.0",
                    type: "HTTP_PROXY",
                    uri: "https://ip-ranges.amazonaws.com/ip-ranges.json",
                },
            },
        },
    },
})});
const exampleDeployment = new aws.apigateway.Deployment("exampleDeployment", {
    restApi: exampleRestApi.id,
    triggers: {
        redeployment: exampleRestApi.body.apply(body => JSON.stringify(body)).apply(toJSON => crypto.createHash('sha1').update(toJSON).digest('hex')),
    },
});
const exampleStage = new aws.apigateway.Stage("exampleStage", {
    deployment: exampleDeployment.id,
    restApi: exampleRestApi.id,
    stageName: "example",
});
const exampleWebAcl = new aws.wafv2.WebAcl("exampleWebAcl", {
    scope: "REGIONAL",
    defaultAction: {
        allow: {},
    },
    visibilityConfig: {
        cloudwatchMetricsEnabled: false,
        metricName: "friendly-metric-name",
        sampledRequestsEnabled: false,
    },
});
const exampleWebAclAssociation = new aws.wafv2.WebAclAssociation("exampleWebAclAssociation", {
    resourceArn: exampleStage.arn,
    webAclArn: exampleWebAcl.arn,
});
```


{{< /example >}}





{{% /examples %}}




## Create a WebAclAssociation Resource {#create}
{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx">WebAclAssociation</span><span class="p">(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">string</span><span class="p">,</span> <span class="nx">args</span><span class="p">:</span> <span class="nx"><a href="#inputs">WebAclAssociationArgs</a></span><span class="p">,</span> <span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class=nd>@overload</span>
<span class="k">def </span><span class="nx">WebAclAssociation</span><span class="p">(</span><span class="nx">resource_name</span><span class="p">:</span> <span class="nx">str</span><span class="p">,</span>
                      <span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">Optional[ResourceOptions]</a></span> = None<span class="p">,</span>
                      <span class="nx">resource_arn</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                      <span class="nx">web_acl_arn</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">)</span>
<span class=nd>@overload</span>
<span class="k">def </span><span class="nx">WebAclAssociation</span><span class="p">(</span><span class="nx">resource_name</span><span class="p">:</span> <span class="nx">str</span><span class="p">,</span>
                      <span class="nx">args</span><span class="p">:</span> <span class="nx"><a href="#inputs">WebAclAssociationArgs</a></span><span class="p">,</span>
                      <span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">Optional[ResourceOptions]</a></span> = None<span class="p">)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span><span class="nx">NewWebAclAssociation</span><span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">,</span> <span class="nx">name</span><span class="p"> </span><span class="nx">string</span><span class="p">,</span> <span class="nx">args</span><span class="p"> </span><span class="nx"><a href="#inputs">WebAclAssociationArgs</a></span><span class="p">,</span> <span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx">WebAclAssociation</span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx">WebAclAssociation</span><span class="p">(</span><span class="nx">string</span><span class="p"> </span><span class="nx">name<span class="p">,</span> <span class="nx"><a href="#inputs">WebAclAssociationArgs</a></span><span class="p"> </span><span class="nx">args<span class="p">,</span> <span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language nodejs %}}

<dl class="resources-properties"><dt
        class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>The unique name of the resource.</dd><dt
        class="property-required" title="Required">
        <span>args</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#inputs">WebAclAssociationArgs</a></span>
    </dt>
    <dd>The arguments to resource properties.</dd><dt
        class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span>
    </dt>
    <dd>Bag of options to control resource&#39;s behavior.</dd></dl>

{{% /choosable %}}

{{% choosable language python %}}

<dl class="resources-properties"><dt
        class="property-required" title="Required">
        <span>resource_name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>The unique name of the resource.</dd><dt
        class="property-required" title="Required">
        <span>args</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#inputs">WebAclAssociationArgs</a></span>
    </dt>
    <dd>The arguments to resource properties.</dd><dt
        class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">ResourceOptions</a></span>
    </dt>
    <dd>Bag of options to control resource&#39;s behavior.</dd></dl>

{{% /choosable %}}

{{% choosable language go %}}

<dl class="resources-properties"><dt
        class="property-optional" title="Optional">
        <span>ctx</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span>
    </dt>
    <dd>Context object for the current deployment.</dd><dt
        class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>The unique name of the resource.</dd><dt
        class="property-required" title="Required">
        <span>args</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#inputs">WebAclAssociationArgs</a></span>
    </dt>
    <dd>The arguments to resource properties.</dd><dt
        class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span>
    </dt>
    <dd>Bag of options to control resource&#39;s behavior.</dd></dl>

{{% /choosable %}}

{{% choosable language csharp %}}

<dl class="resources-properties"><dt
        class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>The unique name of the resource.</dd><dt
        class="property-required" title="Required">
        <span>args</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#inputs">WebAclAssociationArgs</a></span>
    </dt>
    <dd>The arguments to resource properties.</dd><dt
        class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span>
    </dt>
    <dd>Bag of options to control resource&#39;s behavior.</dd></dl>

{{% /choosable %}}

## WebAclAssociation Resource Properties {#properties}

To learn more about resource properties and how to use them, see [Inputs and Outputs]({{< relref "/docs/intro/concepts/inputs-outputs" >}}) in the Architecture and Concepts docs.

### Inputs

The WebAclAssociation resource accepts the following [input]({{< relref "/docs/intro/concepts/inputs-outputs" >}}) properties:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="resourcearn_csharp">
<a href="#resourcearn_csharp" style="color: inherit; text-decoration: inherit;">Resource<wbr>Arn</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the resource to associate with the web ACL. This must be an ARN of an Application Load Balancer or an Amazon API Gateway stage.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="webaclarn_csharp">
<a href="#webaclarn_csharp" style="color: inherit; text-decoration: inherit;">Web<wbr>Acl<wbr>Arn</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the Web ACL that you want to associate with the resource.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="resourcearn_go">
<a href="#resourcearn_go" style="color: inherit; text-decoration: inherit;">Resource<wbr>Arn</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the resource to associate with the web ACL. This must be an ARN of an Application Load Balancer or an Amazon API Gateway stage.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="webaclarn_go">
<a href="#webaclarn_go" style="color: inherit; text-decoration: inherit;">Web<wbr>Acl<wbr>Arn</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the Web ACL that you want to associate with the resource.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="resourcearn_nodejs">
<a href="#resourcearn_nodejs" style="color: inherit; text-decoration: inherit;">resource<wbr>Arn</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the resource to associate with the web ACL. This must be an ARN of an Application Load Balancer or an Amazon API Gateway stage.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="webaclarn_nodejs">
<a href="#webaclarn_nodejs" style="color: inherit; text-decoration: inherit;">web<wbr>Acl<wbr>Arn</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the Web ACL that you want to associate with the resource.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="resource_arn_python">
<a href="#resource_arn_python" style="color: inherit; text-decoration: inherit;">resource_<wbr>arn</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the resource to associate with the web ACL. This must be an ARN of an Application Load Balancer or an Amazon API Gateway stage.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="web_acl_arn_python">
<a href="#web_acl_arn_python" style="color: inherit; text-decoration: inherit;">web_<wbr>acl_<wbr>arn</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the Web ACL that you want to associate with the resource.
{{% /md %}}</dd></dl>
{{% /choosable %}}


### Outputs

All [input](#inputs) properties are implicitly available as output properties. Additionally, the WebAclAssociation resource produces the following output properties:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="id_csharp">
<a href="#id_csharp" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="id_go">
<a href="#id_go" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="id_nodejs">
<a href="#id_nodejs" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="id_python">
<a href="#id_python" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.{{% /md %}}</dd></dl>
{{% /choosable %}}



## Look up an Existing WebAclAssociation Resource {#look-up}

Get an existing WebAclAssociation resource's state with the given name, ID, and optional extra properties used to qualify the lookup.
{{< chooser language "typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">string</span><span class="p">,</span> <span class="nx">id</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">Input&lt;ID&gt;</a></span><span class="p">,</span> <span class="nx">state</span><span class="p">?:</span> <span class="nx">WebAclAssociationState</span><span class="p">,</span> <span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">): </span><span class="nx">WebAclAssociation</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class=nd>@staticmethod</span>
<span class="k">def </span><span class="nf">get</span><span class="p">(</span><span class="nx">resource_name</span><span class="p">:</span> <span class="nx">str</span><span class="p">,</span>
        <span class="nx">id</span><span class="p">:</span> <span class="nx">str</span><span class="p">,</span>
        <span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">Optional[ResourceOptions]</a></span> = None<span class="p">,</span>
        <span class="nx">resource_arn</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
        <span class="nx">web_acl_arn</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">) -&gt;</span> WebAclAssociation</code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetWebAclAssociation<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">,</span> <span class="nx">name</span><span class="p"> </span><span class="nx">string</span><span class="p">,</span> <span class="nx">id</span><span class="p"> </span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#IDInput">IDInput</a></span><span class="p">,</span> <span class="nx">state</span><span class="p"> *</span><span class="nx">WebAclAssociationState</span><span class="p">,</span> <span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx">WebAclAssociation</span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx">WebAclAssociation</span><span class="nf"> Get</span><span class="p">(</span><span class="nx">string</span><span class="p"> </span><span class="nx">name<span class="p">,</span> <span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input-1.html">Input&lt;string&gt;</a></span><span class="p"> </span><span class="nx">id<span class="p">,</span> <span class="nx">WebAclAssociationState</span><span class="p">? </span><span class="nx">state<span class="p">,</span> <span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language nodejs %}}

<dl class="resources-properties">
    <dt class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resulting resource.</dd>
    <dt class="property-required" title="Required">
        <span>id</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The <em>unique</em> provider ID of the resource to lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>state</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>Any extra arguments used during the lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>

{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties">
    <dt class="property-required" title="Required">
        <span>resource_name</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resulting resource.</dd>
    <dt class="property-required" title="Optional">
        <span>id</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The <em>unique</em> provider ID of the resource to lookup.</dd>
</dl>
{{% /choosable %}}

{{% choosable language go %}}

<dl class="resources-properties">
    <dt class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resulting resource.</dd>
    <dt class="property-required" title="Required">
        <span>id</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The <em>unique</em> provider ID of the resource to lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>state</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>Any extra arguments used during the lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>

{{% /choosable %}}

{{% choosable language csharp %}}

<dl class="resources-properties">
    <dt class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resulting resource.</dd>
    <dt class="property-required" title="Required">
        <span>id</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The <em>unique</em> provider ID of the resource to lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>state</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>Any extra arguments used during the lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>

{{% /choosable %}}

The following state arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_resourcearn_csharp">
<a href="#state_resourcearn_csharp" style="color: inherit; text-decoration: inherit;">Resource<wbr>Arn</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the resource to associate with the web ACL. This must be an ARN of an Application Load Balancer or an Amazon API Gateway stage.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_webaclarn_csharp">
<a href="#state_webaclarn_csharp" style="color: inherit; text-decoration: inherit;">Web<wbr>Acl<wbr>Arn</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the Web ACL that you want to associate with the resource.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_resourcearn_go">
<a href="#state_resourcearn_go" style="color: inherit; text-decoration: inherit;">Resource<wbr>Arn</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the resource to associate with the web ACL. This must be an ARN of an Application Load Balancer or an Amazon API Gateway stage.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_webaclarn_go">
<a href="#state_webaclarn_go" style="color: inherit; text-decoration: inherit;">Web<wbr>Acl<wbr>Arn</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the Web ACL that you want to associate with the resource.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_resourcearn_nodejs">
<a href="#state_resourcearn_nodejs" style="color: inherit; text-decoration: inherit;">resource<wbr>Arn</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the resource to associate with the web ACL. This must be an ARN of an Application Load Balancer or an Amazon API Gateway stage.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_webaclarn_nodejs">
<a href="#state_webaclarn_nodejs" style="color: inherit; text-decoration: inherit;">web<wbr>Acl<wbr>Arn</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the Web ACL that you want to associate with the resource.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_resource_arn_python">
<a href="#state_resource_arn_python" style="color: inherit; text-decoration: inherit;">resource_<wbr>arn</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the resource to associate with the web ACL. This must be an ARN of an Application Load Balancer or an Amazon API Gateway stage.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_web_acl_arn_python">
<a href="#state_web_acl_arn_python" style="color: inherit; text-decoration: inherit;">web_<wbr>acl_<wbr>arn</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the Web ACL that you want to associate with the resource.
{{% /md %}}</dd></dl>
{{% /choosable %}}





## Import


WAFv2 Web ACL Association can be imported using `WEB_ACL_ARN,RESOURCE_ARN` e.g.

```sh
 $ pulumi import aws:wafv2/webAclAssociation:WebAclAssociation example arn:aws:wafv2:...7ce849ea,arn:aws:apigateway:...ages/name
```




<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-aws">https://github.com/pulumi/pulumi-aws</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`aws` Terraform Provider](https://github.com/terraform-providers/terraform-provider-aws).{{% /md %}}</dd>
</dl>
