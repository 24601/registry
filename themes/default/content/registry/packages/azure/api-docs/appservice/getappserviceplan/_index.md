
---
title: "getAppServicePlan"
title_tag: "azure.appservice.getAppServicePlan"
meta_desc: "Documentation for the azure.appservice.getAppServicePlan function with examples, input properties, output properties, and supporting types."
layout: api
no_edit_this_page: true
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Use this data source to access information about an existing App Service Plan (formerly known as a `Server Farm`).


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
        var example = Output.Create(Azure.AppService.GetAppServicePlan.InvokeAsync(new Azure.AppService.GetAppServicePlanArgs
        {
            Name = "search-app-service-plan",
            ResourceGroupName = "search-service",
        }));
        this.AppServicePlanId = example.Apply(example => example.Id);
    }

    [Output("appServicePlanId")]
    public Output<string> AppServicePlanId { get; set; }
}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-azure/sdk/v4/go/azure/appservice"
	"github.com/pulumi/pulumi/sdk/v3/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		example, err := appservice.GetAppServicePlan(ctx, &appservice.GetAppServicePlanArgs{
			Name:              "search-app-service-plan",
			ResourceGroupName: "search-service",
		}, nil)
		if err != nil {
			return err
		}
		ctx.Export("appServicePlanId", example.Id)
		return nil
	})
}
```


{{< /example >}}


{{< example python >}}

```python
import pulumi
import pulumi_azure as azure

example = azure.appservice.get_app_service_plan(name="search-app-service-plan",
    resource_group_name="search-service")
pulumi.export("appServicePlanId", example.id)
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as azure from "@pulumi/azure";

const example = azure.appservice.getAppServicePlan({
    name: "search-app-service-plan",
    resourceGroupName: "search-service",
});
export const appServicePlanId = example.then(example => example.id);
```


{{< /example >}}





{{% /examples %}}




## Using getAppServicePlan {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getAppServicePlan<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetAppServicePlanArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetAppServicePlanResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_app_service_plan(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                         <span class="nx">resource_group_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                         <span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetAppServicePlanResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetAppServicePlan<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">,</span> <span class="nx">args</span><span class="p"> *</span><span class="nx">GetAppServicePlanArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">GetAppServicePlanResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `GetAppServicePlan` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetAppServicePlan </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetAppServicePlanResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetAppServicePlanArgs</span><span class="p"> </span><span class="nx">args<span class="p">,</span> <span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the App Service Plan.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_csharp">
<a href="#resourcegroupname_csharp" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Name of the Resource Group where the App Service Plan exists.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="name_go">
<a href="#name_go" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the App Service Plan.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_go">
<a href="#resourcegroupname_go" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Name of the Resource Group where the App Service Plan exists.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="name_nodejs">
<a href="#name_nodejs" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the App Service Plan.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_nodejs">
<a href="#resourcegroupname_nodejs" style="color: inherit; text-decoration: inherit;">resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Name of the Resource Group where the App Service Plan exists.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="name_python">
<a href="#name_python" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the App Service Plan.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resource_group_name_python">
<a href="#resource_group_name_python" style="color: inherit; text-decoration: inherit;">resource_<wbr>group_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Name of the Resource Group where the App Service Plan exists.
{{% /md %}}</dd></dl>
{{% /choosable %}}




## getAppServicePlan Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="appserviceenvironmentid_csharp">
<a href="#appserviceenvironmentid_csharp" style="color: inherit; text-decoration: inherit;">App<wbr>Service<wbr>Environment<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the App Service Environment where the App Service Plan is located.
{{% /md %}}</dd><dt class="property-"
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
        <span id="isxenon_csharp">
<a href="#isxenon_csharp" style="color: inherit; text-decoration: inherit;">Is<wbr>Xenon</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A flag that indicates if it's a xenon plan (support for Windows Container)
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="kind_csharp">
<a href="#kind_csharp" style="color: inherit; text-decoration: inherit;">Kind</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Operating System type of the App Service Plan
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="location_csharp">
<a href="#location_csharp" style="color: inherit; text-decoration: inherit;">Location</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Azure location where the App Service Plan exists
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="maximumelasticworkercount_csharp">
<a href="#maximumelasticworkercount_csharp" style="color: inherit; text-decoration: inherit;">Maximum<wbr>Elastic<wbr>Worker<wbr>Count</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The maximum number of total workers allowed for this ElasticScaleEnabled App Service Plan.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="maximumnumberofworkers_csharp">
<a href="#maximumnumberofworkers_csharp" style="color: inherit; text-decoration: inherit;">Maximum<wbr>Number<wbr>Of<wbr>Workers</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The maximum number of workers supported with the App Service Plan's sku.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="persitescaling_csharp">
<a href="#persitescaling_csharp" style="color: inherit; text-decoration: inherit;">Per<wbr>Site<wbr>Scaling</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Can Apps assigned to this App Service Plan be scaled independently?
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="reserved_csharp">
<a href="#reserved_csharp" style="color: inherit; text-decoration: inherit;">Reserved</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Is this App Service Plan `Reserved`?
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="resourcegroupname_csharp">
<a href="#resourcegroupname_csharp" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="sku_csharp">
<a href="#sku_csharp" style="color: inherit; text-decoration: inherit;">Sku</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getappserviceplansku">Get<wbr>App<wbr>Service<wbr>Plan<wbr>Sku</a></span>
    </dt>
    <dd>{{% md %}}A `sku` block as documented below.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="tags_csharp">
<a href="#tags_csharp" style="color: inherit; text-decoration: inherit;">Tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Dictionary&lt;string, string&gt;</span>
    </dt>
    <dd>{{% md %}}A mapping of tags assigned to the resource.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="zoneredundant_csharp">
<a href="#zoneredundant_csharp" style="color: inherit; text-decoration: inherit;">Zone<wbr>Redundant</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}App Service Plan perform availability zone balancing.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="appserviceenvironmentid_go">
<a href="#appserviceenvironmentid_go" style="color: inherit; text-decoration: inherit;">App<wbr>Service<wbr>Environment<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the App Service Environment where the App Service Plan is located.
{{% /md %}}</dd><dt class="property-"
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
        <span id="isxenon_go">
<a href="#isxenon_go" style="color: inherit; text-decoration: inherit;">Is<wbr>Xenon</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A flag that indicates if it's a xenon plan (support for Windows Container)
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="kind_go">
<a href="#kind_go" style="color: inherit; text-decoration: inherit;">Kind</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Operating System type of the App Service Plan
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="location_go">
<a href="#location_go" style="color: inherit; text-decoration: inherit;">Location</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Azure location where the App Service Plan exists
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="maximumelasticworkercount_go">
<a href="#maximumelasticworkercount_go" style="color: inherit; text-decoration: inherit;">Maximum<wbr>Elastic<wbr>Worker<wbr>Count</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The maximum number of total workers allowed for this ElasticScaleEnabled App Service Plan.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="maximumnumberofworkers_go">
<a href="#maximumnumberofworkers_go" style="color: inherit; text-decoration: inherit;">Maximum<wbr>Number<wbr>Of<wbr>Workers</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The maximum number of workers supported with the App Service Plan's sku.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_go">
<a href="#name_go" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="persitescaling_go">
<a href="#persitescaling_go" style="color: inherit; text-decoration: inherit;">Per<wbr>Site<wbr>Scaling</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Can Apps assigned to this App Service Plan be scaled independently?
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="reserved_go">
<a href="#reserved_go" style="color: inherit; text-decoration: inherit;">Reserved</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Is this App Service Plan `Reserved`?
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="resourcegroupname_go">
<a href="#resourcegroupname_go" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="sku_go">
<a href="#sku_go" style="color: inherit; text-decoration: inherit;">Sku</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getappserviceplansku">Get<wbr>App<wbr>Service<wbr>Plan<wbr>Sku</a></span>
    </dt>
    <dd>{{% md %}}A `sku` block as documented below.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="tags_go">
<a href="#tags_go" style="color: inherit; text-decoration: inherit;">Tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}A mapping of tags assigned to the resource.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="zoneredundant_go">
<a href="#zoneredundant_go" style="color: inherit; text-decoration: inherit;">Zone<wbr>Redundant</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}App Service Plan perform availability zone balancing.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="appserviceenvironmentid_nodejs">
<a href="#appserviceenvironmentid_nodejs" style="color: inherit; text-decoration: inherit;">app<wbr>Service<wbr>Environment<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the App Service Environment where the App Service Plan is located.
{{% /md %}}</dd><dt class="property-"
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
        <span id="isxenon_nodejs">
<a href="#isxenon_nodejs" style="color: inherit; text-decoration: inherit;">is<wbr>Xenon</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}A flag that indicates if it's a xenon plan (support for Windows Container)
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="kind_nodejs">
<a href="#kind_nodejs" style="color: inherit; text-decoration: inherit;">kind</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Operating System type of the App Service Plan
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="location_nodejs">
<a href="#location_nodejs" style="color: inherit; text-decoration: inherit;">location</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Azure location where the App Service Plan exists
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="maximumelasticworkercount_nodejs">
<a href="#maximumelasticworkercount_nodejs" style="color: inherit; text-decoration: inherit;">maximum<wbr>Elastic<wbr>Worker<wbr>Count</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The maximum number of total workers allowed for this ElasticScaleEnabled App Service Plan.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="maximumnumberofworkers_nodejs">
<a href="#maximumnumberofworkers_nodejs" style="color: inherit; text-decoration: inherit;">maximum<wbr>Number<wbr>Of<wbr>Workers</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The maximum number of workers supported with the App Service Plan's sku.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_nodejs">
<a href="#name_nodejs" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="persitescaling_nodejs">
<a href="#persitescaling_nodejs" style="color: inherit; text-decoration: inherit;">per<wbr>Site<wbr>Scaling</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Can Apps assigned to this App Service Plan be scaled independently?
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="reserved_nodejs">
<a href="#reserved_nodejs" style="color: inherit; text-decoration: inherit;">reserved</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Is this App Service Plan `Reserved`?
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="resourcegroupname_nodejs">
<a href="#resourcegroupname_nodejs" style="color: inherit; text-decoration: inherit;">resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="sku_nodejs">
<a href="#sku_nodejs" style="color: inherit; text-decoration: inherit;">sku</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getappserviceplansku">Get<wbr>App<wbr>Service<wbr>Plan<wbr>Sku</a></span>
    </dt>
    <dd>{{% md %}}A `sku` block as documented below.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="tags_nodejs">
<a href="#tags_nodejs" style="color: inherit; text-decoration: inherit;">tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags assigned to the resource.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="zoneredundant_nodejs">
<a href="#zoneredundant_nodejs" style="color: inherit; text-decoration: inherit;">zone<wbr>Redundant</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}App Service Plan perform availability zone balancing.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="app_service_environment_id_python">
<a href="#app_service_environment_id_python" style="color: inherit; text-decoration: inherit;">app_<wbr>service_<wbr>environment_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the App Service Environment where the App Service Plan is located.
{{% /md %}}</dd><dt class="property-"
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
        <span id="is_xenon_python">
<a href="#is_xenon_python" style="color: inherit; text-decoration: inherit;">is_<wbr>xenon</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A flag that indicates if it's a xenon plan (support for Windows Container)
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="kind_python">
<a href="#kind_python" style="color: inherit; text-decoration: inherit;">kind</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Operating System type of the App Service Plan
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="location_python">
<a href="#location_python" style="color: inherit; text-decoration: inherit;">location</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Azure location where the App Service Plan exists
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="maximum_elastic_worker_count_python">
<a href="#maximum_elastic_worker_count_python" style="color: inherit; text-decoration: inherit;">maximum_<wbr>elastic_<wbr>worker_<wbr>count</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The maximum number of total workers allowed for this ElasticScaleEnabled App Service Plan.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="maximum_number_of_workers_python">
<a href="#maximum_number_of_workers_python" style="color: inherit; text-decoration: inherit;">maximum_<wbr>number_<wbr>of_<wbr>workers</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The maximum number of workers supported with the App Service Plan's sku.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_python">
<a href="#name_python" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="per_site_scaling_python">
<a href="#per_site_scaling_python" style="color: inherit; text-decoration: inherit;">per_<wbr>site_<wbr>scaling</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Can Apps assigned to this App Service Plan be scaled independently?
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="reserved_python">
<a href="#reserved_python" style="color: inherit; text-decoration: inherit;">reserved</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Is this App Service Plan `Reserved`?
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="resource_group_name_python">
<a href="#resource_group_name_python" style="color: inherit; text-decoration: inherit;">resource_<wbr>group_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="sku_python">
<a href="#sku_python" style="color: inherit; text-decoration: inherit;">sku</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getappserviceplansku">Get<wbr>App<wbr>Service<wbr>Plan<wbr>Sku</a></span>
    </dt>
    <dd>{{% md %}}A `sku` block as documented below.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="tags_python">
<a href="#tags_python" style="color: inherit; text-decoration: inherit;">tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Mapping[str, str]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags assigned to the resource.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="zone_redundant_python">
<a href="#zone_redundant_python" style="color: inherit; text-decoration: inherit;">zone_<wbr>redundant</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}App Service Plan perform availability zone balancing.
{{% /md %}}</dd></dl>
{{% /choosable %}}




## Supporting Types


<h4 id="getappserviceplansku">Get<wbr>App<wbr>Service<wbr>Plan<wbr>Sku</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="capacity_csharp">
<a href="#capacity_csharp" style="color: inherit; text-decoration: inherit;">Capacity</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Specifies the number of workers associated with this App Service Plan.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="size_csharp">
<a href="#size_csharp" style="color: inherit; text-decoration: inherit;">Size</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the plan's instance size.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="tier_csharp">
<a href="#tier_csharp" style="color: inherit; text-decoration: inherit;">Tier</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the plan's pricing tier.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="capacity_go">
<a href="#capacity_go" style="color: inherit; text-decoration: inherit;">Capacity</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Specifies the number of workers associated with this App Service Plan.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="size_go">
<a href="#size_go" style="color: inherit; text-decoration: inherit;">Size</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the plan's instance size.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="tier_go">
<a href="#tier_go" style="color: inherit; text-decoration: inherit;">Tier</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the plan's pricing tier.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="capacity_nodejs">
<a href="#capacity_nodejs" style="color: inherit; text-decoration: inherit;">capacity</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Specifies the number of workers associated with this App Service Plan.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="size_nodejs">
<a href="#size_nodejs" style="color: inherit; text-decoration: inherit;">size</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the plan's instance size.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="tier_nodejs">
<a href="#tier_nodejs" style="color: inherit; text-decoration: inherit;">tier</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the plan's pricing tier.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="capacity_python">
<a href="#capacity_python" style="color: inherit; text-decoration: inherit;">capacity</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Specifies the number of workers associated with this App Service Plan.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="size_python">
<a href="#size_python" style="color: inherit; text-decoration: inherit;">size</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the plan's instance size.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="tier_python">
<a href="#tier_python" style="color: inherit; text-decoration: inherit;">tier</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the plan's pricing tier.
{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-azure">https://github.com/pulumi/pulumi-azure</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`azurerm` Terraform Provider](https://github.com/hashicorp/terraform-provider-azurerm).{{% /md %}}</dd>
</dl>
