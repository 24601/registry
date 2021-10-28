
---
title: "getAppEngineService"
title_tag: "gcp.monitoring.getAppEngineService"
meta_desc: "Documentation for the gcp.monitoring.getAppEngineService function with examples, input properties, output properties, and supporting types."
layout: api
no_edit_this_page: true
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

A Monitoring Service is the root resource under which operational aspects of a
generic service are accessible. A service is some discrete, autonomous, and
network-accessible unit, designed to solve an individual concern

An App Engine monitoring service is automatically created by GCP to monitor
App Engine services.

To get more information about Service, see:

* [API documentation](https://cloud.google.com/monitoring/api/ref_v3/rest/v3/services)
* How-to Guides
    * [Service Monitoring](https://cloud.google.com/monitoring/service-monitoring)
    * [Monitoring API Documentation](https://cloud.google.com/monitoring/api/v3/)


{{% examples %}}

## Example Usage

{{< chooser language "typescript,python,go,csharp" / >}}


### Monitoring App Engine Service


{{< example csharp >}}

```csharp
using Pulumi;
using Gcp = Pulumi.Gcp;

class MyStack : Stack
{
    public MyStack()
    {
        var bucket = new Gcp.Storage.Bucket("bucket", new Gcp.Storage.BucketArgs
        {
        });
        var @object = new Gcp.Storage.BucketObject("object", new Gcp.Storage.BucketObjectArgs
        {
            Bucket = bucket.Name,
            Source = new FileAsset("./test-fixtures/appengine/hello-world.zip"),
        });
        var myapp = new Gcp.AppEngine.StandardAppVersion("myapp", new Gcp.AppEngine.StandardAppVersionArgs
        {
            VersionId = "v1",
            Service = "myapp",
            Runtime = "nodejs10",
            Entrypoint = new Gcp.AppEngine.Inputs.StandardAppVersionEntrypointArgs
            {
                Shell = "node ./app.js",
            },
            Deployment = new Gcp.AppEngine.Inputs.StandardAppVersionDeploymentArgs
            {
                Zip = new Gcp.AppEngine.Inputs.StandardAppVersionDeploymentZipArgs
                {
                    SourceUrl = Output.Tuple(bucket.Name, @object.Name).Apply(values =>
                    {
                        var bucketName = values.Item1;
                        var objectName = values.Item2;
                        return $"https://storage.googleapis.com/{bucketName}/{objectName}";
                    }),
                },
            },
            EnvVariables = 
            {
                { "port", "8080" },
            },
            DeleteServiceOnDestroy = false,
        });
        var srv = myapp.Service.Apply(service => Gcp.Monitoring.GetAppEngineService.InvokeAsync(new Gcp.Monitoring.GetAppEngineServiceArgs
        {
            ModuleId = service,
        }));
    }

}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"fmt"

	"github.com/pulumi/pulumi-gcp/sdk/v5/go/gcp/appengine"
	"github.com/pulumi/pulumi-gcp/sdk/v5/go/gcp/monitoring"
	"github.com/pulumi/pulumi-gcp/sdk/v5/go/gcp/storage"
	"github.com/pulumi/pulumi/sdk/v3/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		bucket, err := storage.NewBucket(ctx, "bucket", nil)
		if err != nil {
			return err
		}
		object, err := storage.NewBucketObject(ctx, "object", &storage.BucketObjectArgs{
			Bucket: bucket.Name,
			Source: pulumi.NewFileAsset("./test-fixtures/appengine/hello-world.zip"),
		})
		if err != nil {
			return err
		}
		myapp, err := appengine.NewStandardAppVersion(ctx, "myapp", &appengine.StandardAppVersionArgs{
			VersionId: pulumi.String("v1"),
			Service:   pulumi.String("myapp"),
			Runtime:   pulumi.String("nodejs10"),
			Entrypoint: &appengine.StandardAppVersionEntrypointArgs{
				Shell: pulumi.String("node ./app.js"),
			},
			Deployment: &appengine.StandardAppVersionDeploymentArgs{
				Zip: &appengine.StandardAppVersionDeploymentZipArgs{
					SourceUrl: pulumi.All(bucket.Name, object.Name).ApplyT(func(_args []interface{}) (string, error) {
						bucketName := _args[0].(string)
						objectName := _args[1].(string)
						return fmt.Sprintf("%v%v%v%v", "https://storage.googleapis.com/", bucketName, "/", objectName), nil
					}).(pulumi.StringOutput),
				},
			},
			EnvVariables: pulumi.StringMap{
				"port": pulumi.String("8080"),
			},
			DeleteServiceOnDestroy: pulumi.Bool(false),
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
import pulumi_gcp as gcp

bucket = gcp.storage.Bucket("bucket")
object = gcp.storage.BucketObject("object",
    bucket=bucket.name,
    source=pulumi.FileAsset("./test-fixtures/appengine/hello-world.zip"))
myapp = gcp.appengine.StandardAppVersion("myapp",
    version_id="v1",
    service="myapp",
    runtime="nodejs10",
    entrypoint=gcp.appengine.StandardAppVersionEntrypointArgs(
        shell="node ./app.js",
    ),
    deployment=gcp.appengine.StandardAppVersionDeploymentArgs(
        zip=gcp.appengine.StandardAppVersionDeploymentZipArgs(
            source_url=pulumi.Output.all(bucket.name, object.name).apply(lambda bucketName, objectName: f"https://storage.googleapis.com/{bucket_name}/{object_name}"),
        ),
    ),
    env_variables={
        "port": "8080",
    },
    delete_service_on_destroy=False)
srv = myapp.service.apply(lambda service: gcp.monitoring.get_app_engine_service(module_id=service))
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as gcp from "@pulumi/gcp";

const bucket = new gcp.storage.Bucket("bucket", {});
const object = new gcp.storage.BucketObject("object", {
    bucket: bucket.name,
    source: new pulumi.asset.FileAsset("./test-fixtures/appengine/hello-world.zip"),
});
const myapp = new gcp.appengine.StandardAppVersion("myapp", {
    versionId: "v1",
    service: "myapp",
    runtime: "nodejs10",
    entrypoint: {
        shell: "node ./app.js",
    },
    deployment: {
        zip: {
            sourceUrl: pulumi.interpolate`https://storage.googleapis.com/${bucket.name}/${object.name}`,
        },
    },
    envVariables: {
        port: "8080",
    },
    deleteServiceOnDestroy: false,
});
const srv = myapp.service.apply(service => gcp.monitoring.getAppEngineService({
    moduleId: service,
}));
```


{{< /example >}}





{{% /examples %}}




## Using getAppEngineService {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getAppEngineService<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetAppEngineServiceArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetAppEngineServiceResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_app_engine_service(</span><span class="nx">module_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                           <span class="nx">project</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                           <span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetAppEngineServiceResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetAppEngineService<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">,</span> <span class="nx">args</span><span class="p"> *</span><span class="nx">GetAppEngineServiceArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">GetAppEngineServiceResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `GetAppEngineService` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetAppEngineService </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetAppEngineServiceResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetAppEngineServiceArgs</span><span class="p"> </span><span class="nx">args<span class="p">,</span> <span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="moduleid_csharp">
<a href="#moduleid_csharp" style="color: inherit; text-decoration: inherit;">Module<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the App Engine module underlying this
service. Corresponds to the moduleId resource label in the [gae_app](https://cloud.google.com/monitoring/api/resources#tag_gae_app) monitored resource, or the service/module name.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="project_csharp">
<a href="#project_csharp" style="color: inherit; text-decoration: inherit;">Project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="moduleid_go">
<a href="#moduleid_go" style="color: inherit; text-decoration: inherit;">Module<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the App Engine module underlying this
service. Corresponds to the moduleId resource label in the [gae_app](https://cloud.google.com/monitoring/api/resources#tag_gae_app) monitored resource, or the service/module name.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="project_go">
<a href="#project_go" style="color: inherit; text-decoration: inherit;">Project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="moduleid_nodejs">
<a href="#moduleid_nodejs" style="color: inherit; text-decoration: inherit;">module<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the App Engine module underlying this
service. Corresponds to the moduleId resource label in the [gae_app](https://cloud.google.com/monitoring/api/resources#tag_gae_app) monitored resource, or the service/module name.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="project_nodejs">
<a href="#project_nodejs" style="color: inherit; text-decoration: inherit;">project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="module_id_python">
<a href="#module_id_python" style="color: inherit; text-decoration: inherit;">module_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the App Engine module underlying this
service. Corresponds to the moduleId resource label in the [gae_app](https://cloud.google.com/monitoring/api/resources#tag_gae_app) monitored resource, or the service/module name.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="project_python">
<a href="#project_python" style="color: inherit; text-decoration: inherit;">project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
{{% /md %}}</dd></dl>
{{% /choosable %}}




## getAppEngineService Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="displayname_csharp">
<a href="#displayname_csharp" style="color: inherit; text-decoration: inherit;">Display<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="id_csharp">
<a href="#id_csharp" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="moduleid_csharp">
<a href="#moduleid_csharp" style="color: inherit; text-decoration: inherit;">Module<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="serviceid_csharp">
<a href="#serviceid_csharp" style="color: inherit; text-decoration: inherit;">Service<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="telemetries_csharp">
<a href="#telemetries_csharp" style="color: inherit; text-decoration: inherit;">Telemetries</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getappengineservicetelemetry">List&lt;Get<wbr>App<wbr>Engine<wbr>Service<wbr>Telemetry&gt;</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="project_csharp">
<a href="#project_csharp" style="color: inherit; text-decoration: inherit;">Project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="displayname_go">
<a href="#displayname_go" style="color: inherit; text-decoration: inherit;">Display<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="id_go">
<a href="#id_go" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="moduleid_go">
<a href="#moduleid_go" style="color: inherit; text-decoration: inherit;">Module<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_go">
<a href="#name_go" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="serviceid_go">
<a href="#serviceid_go" style="color: inherit; text-decoration: inherit;">Service<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="telemetries_go">
<a href="#telemetries_go" style="color: inherit; text-decoration: inherit;">Telemetries</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getappengineservicetelemetry">[]Get<wbr>App<wbr>Engine<wbr>Service<wbr>Telemetry</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="project_go">
<a href="#project_go" style="color: inherit; text-decoration: inherit;">Project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="displayname_nodejs">
<a href="#displayname_nodejs" style="color: inherit; text-decoration: inherit;">display<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="id_nodejs">
<a href="#id_nodejs" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="moduleid_nodejs">
<a href="#moduleid_nodejs" style="color: inherit; text-decoration: inherit;">module<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_nodejs">
<a href="#name_nodejs" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="serviceid_nodejs">
<a href="#serviceid_nodejs" style="color: inherit; text-decoration: inherit;">service<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="telemetries_nodejs">
<a href="#telemetries_nodejs" style="color: inherit; text-decoration: inherit;">telemetries</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getappengineservicetelemetry">Get<wbr>App<wbr>Engine<wbr>Service<wbr>Telemetry[]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="project_nodejs">
<a href="#project_nodejs" style="color: inherit; text-decoration: inherit;">project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="display_name_python">
<a href="#display_name_python" style="color: inherit; text-decoration: inherit;">display_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="id_python">
<a href="#id_python" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="module_id_python">
<a href="#module_id_python" style="color: inherit; text-decoration: inherit;">module_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_python">
<a href="#name_python" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="service_id_python">
<a href="#service_id_python" style="color: inherit; text-decoration: inherit;">service_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="telemetries_python">
<a href="#telemetries_python" style="color: inherit; text-decoration: inherit;">telemetries</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getappengineservicetelemetry">Sequence[Get<wbr>App<wbr>Engine<wbr>Service<wbr>Telemetry]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="project_python">
<a href="#project_python" style="color: inherit; text-decoration: inherit;">project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}




## Supporting Types


<h4 id="getappengineservicetelemetry">Get<wbr>App<wbr>Engine<wbr>Service<wbr>Telemetry</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="resourcename_csharp">
<a href="#resourcename_csharp" style="color: inherit; text-decoration: inherit;">Resource<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="resourcename_go">
<a href="#resourcename_go" style="color: inherit; text-decoration: inherit;">Resource<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="resourcename_nodejs">
<a href="#resourcename_nodejs" style="color: inherit; text-decoration: inherit;">resource<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="resource_name_python">
<a href="#resource_name_python" style="color: inherit; text-decoration: inherit;">resource_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-gcp">https://github.com/pulumi/pulumi-gcp</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`google-beta` Terraform Provider](https://github.com/hashicorp/terraform-provider-google-beta).{{% /md %}}</dd>
</dl>
