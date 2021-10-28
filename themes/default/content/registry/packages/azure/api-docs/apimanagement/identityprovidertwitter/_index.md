
---
title: "IdentityProviderTwitter"
title_tag: "azure.apimanagement.IdentityProviderTwitter"
meta_desc: "Documentation for the azure.apimanagement.IdentityProviderTwitter resource with examples, input properties, output properties, lookup functions, and supporting types."
layout: api
no_edit_this_page: true
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Manages an API Management Twitter Identity Provider.

{{% examples %}}

## Example Usage

{{< chooser language "typescript,python,go,csharp" / >}}





{{< example csharp >}}

```csharp
using Pulumi;
using Azure = Pulumi.Azure;

class MyStack : Stack
{
    public MyStack()
    {
        var exampleResourceGroup = new Azure.Core.ResourceGroup("exampleResourceGroup", new Azure.Core.ResourceGroupArgs
        {
            Location = "West Europe",
        });
        var exampleService = new Azure.ApiManagement.Service("exampleService", new Azure.ApiManagement.ServiceArgs
        {
            Location = exampleResourceGroup.Location,
            ResourceGroupName = exampleResourceGroup.Name,
            PublisherName = "My Company",
            PublisherEmail = "company@mycompany.io",
            SkuName = "Developer_1",
        });
        var exampleIdentityProviderTwitter = new Azure.ApiManagement.IdentityProviderTwitter("exampleIdentityProviderTwitter", new Azure.ApiManagement.IdentityProviderTwitterArgs
        {
            ResourceGroupName = exampleResourceGroup.Name,
            ApiManagementName = exampleService.Name,
            ApiKey = "00000000000000000000000000000000",
            ApiSecretKey = "00000000000000000000000000000000",
        });
    }

}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-azure/sdk/v4/go/azure/apimanagement"
	"github.com/pulumi/pulumi-azure/sdk/v4/go/azure/core"
	"github.com/pulumi/pulumi/sdk/v3/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		exampleResourceGroup, err := core.NewResourceGroup(ctx, "exampleResourceGroup", &core.ResourceGroupArgs{
			Location: pulumi.String("West Europe"),
		})
		if err != nil {
			return err
		}
		exampleService, err := apimanagement.NewService(ctx, "exampleService", &apimanagement.ServiceArgs{
			Location:          exampleResourceGroup.Location,
			ResourceGroupName: exampleResourceGroup.Name,
			PublisherName:     pulumi.String("My Company"),
			PublisherEmail:    pulumi.String("company@mycompany.io"),
			SkuName:           pulumi.String("Developer_1"),
		})
		if err != nil {
			return err
		}
		_, err = apimanagement.NewIdentityProviderTwitter(ctx, "exampleIdentityProviderTwitter", &apimanagement.IdentityProviderTwitterArgs{
			ResourceGroupName: exampleResourceGroup.Name,
			ApiManagementName: exampleService.Name,
			ApiKey:            pulumi.String("00000000000000000000000000000000"),
			ApiSecretKey:      pulumi.String("00000000000000000000000000000000"),
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
import pulumi_azure as azure

example_resource_group = azure.core.ResourceGroup("exampleResourceGroup", location="West Europe")
example_service = azure.apimanagement.Service("exampleService",
    location=example_resource_group.location,
    resource_group_name=example_resource_group.name,
    publisher_name="My Company",
    publisher_email="company@mycompany.io",
    sku_name="Developer_1")
example_identity_provider_twitter = azure.apimanagement.IdentityProviderTwitter("exampleIdentityProviderTwitter",
    resource_group_name=example_resource_group.name,
    api_management_name=example_service.name,
    api_key="00000000000000000000000000000000",
    api_secret_key="00000000000000000000000000000000")
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as azure from "@pulumi/azure";

const exampleResourceGroup = new azure.core.ResourceGroup("exampleResourceGroup", {location: "West Europe"});
const exampleService = new azure.apimanagement.Service("exampleService", {
    location: exampleResourceGroup.location,
    resourceGroupName: exampleResourceGroup.name,
    publisherName: "My Company",
    publisherEmail: "company@mycompany.io",
    skuName: "Developer_1",
});
const exampleIdentityProviderTwitter = new azure.apimanagement.IdentityProviderTwitter("exampleIdentityProviderTwitter", {
    resourceGroupName: exampleResourceGroup.name,
    apiManagementName: exampleService.name,
    apiKey: "00000000000000000000000000000000",
    apiSecretKey: "00000000000000000000000000000000",
});
```


{{< /example >}}





{{% /examples %}}




## Create a IdentityProviderTwitter Resource {#create}
{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx">IdentityProviderTwitter</span><span class="p">(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">string</span><span class="p">,</span> <span class="nx">args</span><span class="p">:</span> <span class="nx"><a href="#inputs">IdentityProviderTwitterArgs</a></span><span class="p">,</span> <span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class=nd>@overload</span>
<span class="k">def </span><span class="nx">IdentityProviderTwitter</span><span class="p">(</span><span class="nx">resource_name</span><span class="p">:</span> <span class="nx">str</span><span class="p">,</span>
                            <span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">Optional[ResourceOptions]</a></span> = None<span class="p">,</span>
                            <span class="nx">api_key</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                            <span class="nx">api_management_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                            <span class="nx">api_secret_key</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                            <span class="nx">resource_group_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">)</span>
<span class=nd>@overload</span>
<span class="k">def </span><span class="nx">IdentityProviderTwitter</span><span class="p">(</span><span class="nx">resource_name</span><span class="p">:</span> <span class="nx">str</span><span class="p">,</span>
                            <span class="nx">args</span><span class="p">:</span> <span class="nx"><a href="#inputs">IdentityProviderTwitterArgs</a></span><span class="p">,</span>
                            <span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">Optional[ResourceOptions]</a></span> = None<span class="p">)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span><span class="nx">NewIdentityProviderTwitter</span><span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">,</span> <span class="nx">name</span><span class="p"> </span><span class="nx">string</span><span class="p">,</span> <span class="nx">args</span><span class="p"> </span><span class="nx"><a href="#inputs">IdentityProviderTwitterArgs</a></span><span class="p">,</span> <span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx">IdentityProviderTwitter</span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx">IdentityProviderTwitter</span><span class="p">(</span><span class="nx">string</span><span class="p"> </span><span class="nx">name<span class="p">,</span> <span class="nx"><a href="#inputs">IdentityProviderTwitterArgs</a></span><span class="p"> </span><span class="nx">args<span class="p">,</span> <span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
        <span class="property-type"><a href="#inputs">IdentityProviderTwitterArgs</a></span>
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
        <span class="property-type"><a href="#inputs">IdentityProviderTwitterArgs</a></span>
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
        <span class="property-type"><a href="#inputs">IdentityProviderTwitterArgs</a></span>
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
        <span class="property-type"><a href="#inputs">IdentityProviderTwitterArgs</a></span>
    </dt>
    <dd>The arguments to resource properties.</dd><dt
        class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span>
    </dt>
    <dd>Bag of options to control resource&#39;s behavior.</dd></dl>

{{% /choosable %}}

## IdentityProviderTwitter Resource Properties {#properties}

To learn more about resource properties and how to use them, see [Inputs and Outputs]({{< relref "/docs/intro/concepts/inputs-outputs" >}}) in the Architecture and Concepts docs.

### Inputs

The IdentityProviderTwitter resource accepts the following [input]({{< relref "/docs/intro/concepts/inputs-outputs" >}}) properties:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="apikey_csharp">
<a href="#apikey_csharp" style="color: inherit; text-decoration: inherit;">Api<wbr>Key</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}App Consumer API key for Twitter.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="apimanagementname_csharp">
<a href="#apimanagementname_csharp" style="color: inherit; text-decoration: inherit;">Api<wbr>Management<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Name of the API Management Service where this Twitter Identity Provider should be created. Changing this forces a new resource to be created.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="apisecretkey_csharp">
<a href="#apisecretkey_csharp" style="color: inherit; text-decoration: inherit;">Api<wbr>Secret<wbr>Key</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}App Consumer API secret key for Twitter.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_csharp">
<a href="#resourcegroupname_csharp" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Name of the Resource Group where the API Management Service exists. Changing this forces a new resource to be created.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="apikey_go">
<a href="#apikey_go" style="color: inherit; text-decoration: inherit;">Api<wbr>Key</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}App Consumer API key for Twitter.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="apimanagementname_go">
<a href="#apimanagementname_go" style="color: inherit; text-decoration: inherit;">Api<wbr>Management<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Name of the API Management Service where this Twitter Identity Provider should be created. Changing this forces a new resource to be created.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="apisecretkey_go">
<a href="#apisecretkey_go" style="color: inherit; text-decoration: inherit;">Api<wbr>Secret<wbr>Key</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}App Consumer API secret key for Twitter.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_go">
<a href="#resourcegroupname_go" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Name of the Resource Group where the API Management Service exists. Changing this forces a new resource to be created.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="apikey_nodejs">
<a href="#apikey_nodejs" style="color: inherit; text-decoration: inherit;">api<wbr>Key</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}App Consumer API key for Twitter.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="apimanagementname_nodejs">
<a href="#apimanagementname_nodejs" style="color: inherit; text-decoration: inherit;">api<wbr>Management<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Name of the API Management Service where this Twitter Identity Provider should be created. Changing this forces a new resource to be created.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="apisecretkey_nodejs">
<a href="#apisecretkey_nodejs" style="color: inherit; text-decoration: inherit;">api<wbr>Secret<wbr>Key</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}App Consumer API secret key for Twitter.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_nodejs">
<a href="#resourcegroupname_nodejs" style="color: inherit; text-decoration: inherit;">resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Name of the Resource Group where the API Management Service exists. Changing this forces a new resource to be created.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="api_key_python">
<a href="#api_key_python" style="color: inherit; text-decoration: inherit;">api_<wbr>key</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}App Consumer API key for Twitter.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="api_management_name_python">
<a href="#api_management_name_python" style="color: inherit; text-decoration: inherit;">api_<wbr>management_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Name of the API Management Service where this Twitter Identity Provider should be created. Changing this forces a new resource to be created.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="api_secret_key_python">
<a href="#api_secret_key_python" style="color: inherit; text-decoration: inherit;">api_<wbr>secret_<wbr>key</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}App Consumer API secret key for Twitter.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resource_group_name_python">
<a href="#resource_group_name_python" style="color: inherit; text-decoration: inherit;">resource_<wbr>group_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Name of the Resource Group where the API Management Service exists. Changing this forces a new resource to be created.
{{% /md %}}</dd></dl>
{{% /choosable %}}


### Outputs

All [input](#inputs) properties are implicitly available as output properties. Additionally, the IdentityProviderTwitter resource produces the following output properties:



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



## Look up an Existing IdentityProviderTwitter Resource {#look-up}

Get an existing IdentityProviderTwitter resource's state with the given name, ID, and optional extra properties used to qualify the lookup.
{{< chooser language "typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">string</span><span class="p">,</span> <span class="nx">id</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">Input&lt;ID&gt;</a></span><span class="p">,</span> <span class="nx">state</span><span class="p">?:</span> <span class="nx">IdentityProviderTwitterState</span><span class="p">,</span> <span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">): </span><span class="nx">IdentityProviderTwitter</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class=nd>@staticmethod</span>
<span class="k">def </span><span class="nf">get</span><span class="p">(</span><span class="nx">resource_name</span><span class="p">:</span> <span class="nx">str</span><span class="p">,</span>
        <span class="nx">id</span><span class="p">:</span> <span class="nx">str</span><span class="p">,</span>
        <span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">Optional[ResourceOptions]</a></span> = None<span class="p">,</span>
        <span class="nx">api_key</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
        <span class="nx">api_management_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
        <span class="nx">api_secret_key</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
        <span class="nx">resource_group_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">) -&gt;</span> IdentityProviderTwitter</code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetIdentityProviderTwitter<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">,</span> <span class="nx">name</span><span class="p"> </span><span class="nx">string</span><span class="p">,</span> <span class="nx">id</span><span class="p"> </span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#IDInput">IDInput</a></span><span class="p">,</span> <span class="nx">state</span><span class="p"> *</span><span class="nx">IdentityProviderTwitterState</span><span class="p">,</span> <span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx">IdentityProviderTwitter</span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx">IdentityProviderTwitter</span><span class="nf"> Get</span><span class="p">(</span><span class="nx">string</span><span class="p"> </span><span class="nx">name<span class="p">,</span> <span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input-1.html">Input&lt;string&gt;</a></span><span class="p"> </span><span class="nx">id<span class="p">,</span> <span class="nx">IdentityProviderTwitterState</span><span class="p">? </span><span class="nx">state<span class="p">,</span> <span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
        <span id="state_apikey_csharp">
<a href="#state_apikey_csharp" style="color: inherit; text-decoration: inherit;">Api<wbr>Key</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}App Consumer API key for Twitter.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_apimanagementname_csharp">
<a href="#state_apimanagementname_csharp" style="color: inherit; text-decoration: inherit;">Api<wbr>Management<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Name of the API Management Service where this Twitter Identity Provider should be created. Changing this forces a new resource to be created.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_apisecretkey_csharp">
<a href="#state_apisecretkey_csharp" style="color: inherit; text-decoration: inherit;">Api<wbr>Secret<wbr>Key</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}App Consumer API secret key for Twitter.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_resourcegroupname_csharp">
<a href="#state_resourcegroupname_csharp" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Name of the Resource Group where the API Management Service exists. Changing this forces a new resource to be created.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_apikey_go">
<a href="#state_apikey_go" style="color: inherit; text-decoration: inherit;">Api<wbr>Key</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}App Consumer API key for Twitter.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_apimanagementname_go">
<a href="#state_apimanagementname_go" style="color: inherit; text-decoration: inherit;">Api<wbr>Management<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Name of the API Management Service where this Twitter Identity Provider should be created. Changing this forces a new resource to be created.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_apisecretkey_go">
<a href="#state_apisecretkey_go" style="color: inherit; text-decoration: inherit;">Api<wbr>Secret<wbr>Key</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}App Consumer API secret key for Twitter.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_resourcegroupname_go">
<a href="#state_resourcegroupname_go" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Name of the Resource Group where the API Management Service exists. Changing this forces a new resource to be created.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_apikey_nodejs">
<a href="#state_apikey_nodejs" style="color: inherit; text-decoration: inherit;">api<wbr>Key</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}App Consumer API key for Twitter.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_apimanagementname_nodejs">
<a href="#state_apimanagementname_nodejs" style="color: inherit; text-decoration: inherit;">api<wbr>Management<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Name of the API Management Service where this Twitter Identity Provider should be created. Changing this forces a new resource to be created.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_apisecretkey_nodejs">
<a href="#state_apisecretkey_nodejs" style="color: inherit; text-decoration: inherit;">api<wbr>Secret<wbr>Key</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}App Consumer API secret key for Twitter.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_resourcegroupname_nodejs">
<a href="#state_resourcegroupname_nodejs" style="color: inherit; text-decoration: inherit;">resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Name of the Resource Group where the API Management Service exists. Changing this forces a new resource to be created.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_api_key_python">
<a href="#state_api_key_python" style="color: inherit; text-decoration: inherit;">api_<wbr>key</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}App Consumer API key for Twitter.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_api_management_name_python">
<a href="#state_api_management_name_python" style="color: inherit; text-decoration: inherit;">api_<wbr>management_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Name of the API Management Service where this Twitter Identity Provider should be created. Changing this forces a new resource to be created.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_api_secret_key_python">
<a href="#state_api_secret_key_python" style="color: inherit; text-decoration: inherit;">api_<wbr>secret_<wbr>key</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}App Consumer API secret key for Twitter.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_resource_group_name_python">
<a href="#state_resource_group_name_python" style="color: inherit; text-decoration: inherit;">resource_<wbr>group_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Name of the Resource Group where the API Management Service exists. Changing this forces a new resource to be created.
{{% /md %}}</dd></dl>
{{% /choosable %}}





## Import


API Management Twitter Identity Provider can be imported using the `resource id`, e.g.

```sh
 $ pulumi import azure:apimanagement/identityProviderTwitter:IdentityProviderTwitter example /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/mygroup1/providers/Microsoft.ApiManagement/service/instance1/identityProviders/twitter
```




<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-azure">https://github.com/pulumi/pulumi-azure</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`azurerm` Terraform Provider](https://github.com/hashicorp/terraform-provider-azurerm).{{% /md %}}</dd>
</dl>
