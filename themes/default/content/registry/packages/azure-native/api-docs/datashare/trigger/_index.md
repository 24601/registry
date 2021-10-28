
---
title: "Trigger"
title_tag: "azure-native.datashare.Trigger"
meta_desc: "Documentation for the azure-native.datashare.Trigger resource with examples, input properties, output properties, lookup functions, and supporting types."
layout: api
no_edit_this_page: true
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->
<p class="resource-deprecated">Deprecated: {{% md %}}Please use one of the variants: ScheduledTrigger.{{% /md %}}</p>

A Trigger data transfer object.
API Version: 2020-09-01.

{{% examples %}}

## Example Usage

{{< chooser language "typescript,python,go,csharp" / >}}


### Triggers_Create


{{< example csharp >}}

```csharp
using Pulumi;
using AzureNative = Pulumi.AzureNative;

class MyStack : Stack
{
    public MyStack()
    {
        var trigger = new AzureNative.DataShare.Trigger("trigger", new AzureNative.DataShare.TriggerArgs
        {
            AccountName = "Account1",
            Kind = "ScheduleBased",
            ResourceGroupName = "SampleResourceGroup",
            ShareSubscriptionName = "ShareSubscription1",
            TriggerName = "Trigger1",
        });
    }

}

```


{{< /example >}}


{{< example go >}}


```go
package main

import (
	datashare "github.com/pulumi/pulumi-azure-native/sdk/go/azure/datashare"
	"github.com/pulumi/pulumi/sdk/v3/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		_, err := datashare.NewTrigger(ctx, "trigger", &datashare.TriggerArgs{
			AccountName:           pulumi.String("Account1"),
			Kind:                  pulumi.String("ScheduleBased"),
			ResourceGroupName:     pulumi.String("SampleResourceGroup"),
			ShareSubscriptionName: pulumi.String("ShareSubscription1"),
			TriggerName:           pulumi.String("Trigger1"),
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
import pulumi_azure_native as azure_native

trigger = azure_native.datashare.Trigger("trigger",
    account_name="Account1",
    kind="ScheduleBased",
    resource_group_name="SampleResourceGroup",
    share_subscription_name="ShareSubscription1",
    trigger_name="Trigger1")

```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as azure_native from "@pulumi/azure-native";

const trigger = new azure_native.datashare.Trigger("trigger", {
    accountName: "Account1",
    kind: "ScheduleBased",
    resourceGroupName: "SampleResourceGroup",
    shareSubscriptionName: "ShareSubscription1",
    triggerName: "Trigger1",
});

```


{{< /example >}}





{{% /examples %}}




## Create a Trigger Resource {#create}
{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx">Trigger</span><span class="p">(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">string</span><span class="p">,</span> <span class="nx">args</span><span class="p">:</span> <span class="nx"><a href="#inputs">TriggerArgs</a></span><span class="p">,</span> <span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class=nd>@overload</span>
<span class="k">def </span><span class="nx">Trigger</span><span class="p">(</span><span class="nx">resource_name</span><span class="p">:</span> <span class="nx">str</span><span class="p">,</span>
            <span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">Optional[ResourceOptions]</a></span> = None<span class="p">,</span>
            <span class="nx">account_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
            <span class="nx">kind</span><span class="p">:</span> <span class="nx">Optional[Union[str, TriggerKind]]</span> = None<span class="p">,</span>
            <span class="nx">resource_group_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
            <span class="nx">share_subscription_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
            <span class="nx">trigger_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">)</span>
<span class=nd>@overload</span>
<span class="k">def </span><span class="nx">Trigger</span><span class="p">(</span><span class="nx">resource_name</span><span class="p">:</span> <span class="nx">str</span><span class="p">,</span>
            <span class="nx">args</span><span class="p">:</span> <span class="nx"><a href="#inputs">TriggerArgs</a></span><span class="p">,</span>
            <span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">Optional[ResourceOptions]</a></span> = None<span class="p">)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span><span class="nx">NewTrigger</span><span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">,</span> <span class="nx">name</span><span class="p"> </span><span class="nx">string</span><span class="p">,</span> <span class="nx">args</span><span class="p"> </span><span class="nx"><a href="#inputs">TriggerArgs</a></span><span class="p">,</span> <span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx">Trigger</span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx">Trigger</span><span class="p">(</span><span class="nx">string</span><span class="p"> </span><span class="nx">name<span class="p">,</span> <span class="nx"><a href="#inputs">TriggerArgs</a></span><span class="p"> </span><span class="nx">args<span class="p">,</span> <span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
        <span class="property-type"><a href="#inputs">TriggerArgs</a></span>
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
        <span class="property-type"><a href="#inputs">TriggerArgs</a></span>
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
        <span class="property-type"><a href="#inputs">TriggerArgs</a></span>
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
        <span class="property-type"><a href="#inputs">TriggerArgs</a></span>
    </dt>
    <dd>The arguments to resource properties.</dd><dt
        class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span>
    </dt>
    <dd>Bag of options to control resource&#39;s behavior.</dd></dl>

{{% /choosable %}}

## Trigger Resource Properties {#properties}

To learn more about resource properties and how to use them, see [Inputs and Outputs]({{< relref "/docs/intro/concepts/inputs-outputs" >}}) in the Architecture and Concepts docs.

### Inputs

The Trigger resource accepts the following [input]({{< relref "/docs/intro/concepts/inputs-outputs" >}}) properties:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="accountname_csharp">
<a href="#accountname_csharp" style="color: inherit; text-decoration: inherit;">Account<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the share account.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="kind_csharp">
<a href="#kind_csharp" style="color: inherit; text-decoration: inherit;">Kind</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string | <a href="#triggerkind">Pulumi.<wbr>Azure<wbr>Native.<wbr>Data<wbr>Share.<wbr>Trigger<wbr>Kind</a></span>
    </dt>
    <dd>{{% md %}}Kind of synchronization on trigger.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_csharp">
<a href="#resourcegroupname_csharp" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource group name.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="sharesubscriptionname_csharp">
<a href="#sharesubscriptionname_csharp" style="color: inherit; text-decoration: inherit;">Share<wbr>Subscription<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the share subscription which will hold the data set sink.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="triggername_csharp">
<a href="#triggername_csharp" style="color: inherit; text-decoration: inherit;">Trigger<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the trigger.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="accountname_go">
<a href="#accountname_go" style="color: inherit; text-decoration: inherit;">Account<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the share account.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="kind_go">
<a href="#kind_go" style="color: inherit; text-decoration: inherit;">Kind</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string | <a href="#triggerkind">Trigger<wbr>Kind</a></span>
    </dt>
    <dd>{{% md %}}Kind of synchronization on trigger.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_go">
<a href="#resourcegroupname_go" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource group name.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="sharesubscriptionname_go">
<a href="#sharesubscriptionname_go" style="color: inherit; text-decoration: inherit;">Share<wbr>Subscription<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the share subscription which will hold the data set sink.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="triggername_go">
<a href="#triggername_go" style="color: inherit; text-decoration: inherit;">Trigger<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the trigger.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="accountname_nodejs">
<a href="#accountname_nodejs" style="color: inherit; text-decoration: inherit;">account<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the share account.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="kind_nodejs">
<a href="#kind_nodejs" style="color: inherit; text-decoration: inherit;">kind</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string | <a href="#triggerkind">Trigger<wbr>Kind</a></span>
    </dt>
    <dd>{{% md %}}Kind of synchronization on trigger.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_nodejs">
<a href="#resourcegroupname_nodejs" style="color: inherit; text-decoration: inherit;">resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource group name.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="sharesubscriptionname_nodejs">
<a href="#sharesubscriptionname_nodejs" style="color: inherit; text-decoration: inherit;">share<wbr>Subscription<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the share subscription which will hold the data set sink.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="triggername_nodejs">
<a href="#triggername_nodejs" style="color: inherit; text-decoration: inherit;">trigger<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the trigger.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="account_name_python">
<a href="#account_name_python" style="color: inherit; text-decoration: inherit;">account_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the share account.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="kind_python">
<a href="#kind_python" style="color: inherit; text-decoration: inherit;">kind</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str | <a href="#triggerkind">Trigger<wbr>Kind</a></span>
    </dt>
    <dd>{{% md %}}Kind of synchronization on trigger.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resource_group_name_python">
<a href="#resource_group_name_python" style="color: inherit; text-decoration: inherit;">resource_<wbr>group_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The resource group name.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="share_subscription_name_python">
<a href="#share_subscription_name_python" style="color: inherit; text-decoration: inherit;">share_<wbr>subscription_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the share subscription which will hold the data set sink.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="trigger_name_python">
<a href="#trigger_name_python" style="color: inherit; text-decoration: inherit;">trigger_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the trigger.{{% /md %}}</dd></dl>
{{% /choosable %}}


### Outputs

All [input](#inputs) properties are implicitly available as output properties. Additionally, the Trigger resource produces the following output properties:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="id_csharp">
<a href="#id_csharp" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the azure resource{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="systemdata_csharp">
<a href="#systemdata_csharp" style="color: inherit; text-decoration: inherit;">System<wbr>Data</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#systemdataresponse">Pulumi.<wbr>Azure<wbr>Native.<wbr>Data<wbr>Share.<wbr>Outputs.<wbr>System<wbr>Data<wbr>Response</a></span>
    </dt>
    <dd>{{% md %}}System Data of the Azure resource.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="type_csharp">
<a href="#type_csharp" style="color: inherit; text-decoration: inherit;">Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Type of the azure resource{{% /md %}}</dd></dl>
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
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_go">
<a href="#name_go" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the azure resource{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="systemdata_go">
<a href="#systemdata_go" style="color: inherit; text-decoration: inherit;">System<wbr>Data</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#systemdataresponse">System<wbr>Data<wbr>Response</a></span>
    </dt>
    <dd>{{% md %}}System Data of the Azure resource.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="type_go">
<a href="#type_go" style="color: inherit; text-decoration: inherit;">Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Type of the azure resource{{% /md %}}</dd></dl>
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
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_nodejs">
<a href="#name_nodejs" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the azure resource{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="systemdata_nodejs">
<a href="#systemdata_nodejs" style="color: inherit; text-decoration: inherit;">system<wbr>Data</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#systemdataresponse">System<wbr>Data<wbr>Response</a></span>
    </dt>
    <dd>{{% md %}}System Data of the Azure resource.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="type_nodejs">
<a href="#type_nodejs" style="color: inherit; text-decoration: inherit;">type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Type of the azure resource{{% /md %}}</dd></dl>
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
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_python">
<a href="#name_python" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the azure resource{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="system_data_python">
<a href="#system_data_python" style="color: inherit; text-decoration: inherit;">system_<wbr>data</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#systemdataresponse">System<wbr>Data<wbr>Response</a></span>
    </dt>
    <dd>{{% md %}}System Data of the Azure resource.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="type_python">
<a href="#type_python" style="color: inherit; text-decoration: inherit;">type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Type of the azure resource{{% /md %}}</dd></dl>
{{% /choosable %}}







## Supporting Types



<h4 id="systemdataresponse">System<wbr>Data<wbr>Response</h4>

{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="createdat_csharp">
<a href="#createdat_csharp" style="color: inherit; text-decoration: inherit;">Created<wbr>At</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The timestamp of resource creation (UTC).{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="createdby_csharp">
<a href="#createdby_csharp" style="color: inherit; text-decoration: inherit;">Created<wbr>By</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The identity that created the resource.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="createdbytype_csharp">
<a href="#createdbytype_csharp" style="color: inherit; text-decoration: inherit;">Created<wbr>By<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of identity that created the resource.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="lastmodifiedat_csharp">
<a href="#lastmodifiedat_csharp" style="color: inherit; text-decoration: inherit;">Last<wbr>Modified<wbr>At</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of identity that last modified the resource.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="lastmodifiedby_csharp">
<a href="#lastmodifiedby_csharp" style="color: inherit; text-decoration: inherit;">Last<wbr>Modified<wbr>By</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The identity that last modified the resource.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="lastmodifiedbytype_csharp">
<a href="#lastmodifiedbytype_csharp" style="color: inherit; text-decoration: inherit;">Last<wbr>Modified<wbr>By<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of identity that last modified the resource.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="createdat_go">
<a href="#createdat_go" style="color: inherit; text-decoration: inherit;">Created<wbr>At</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The timestamp of resource creation (UTC).{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="createdby_go">
<a href="#createdby_go" style="color: inherit; text-decoration: inherit;">Created<wbr>By</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The identity that created the resource.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="createdbytype_go">
<a href="#createdbytype_go" style="color: inherit; text-decoration: inherit;">Created<wbr>By<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of identity that created the resource.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="lastmodifiedat_go">
<a href="#lastmodifiedat_go" style="color: inherit; text-decoration: inherit;">Last<wbr>Modified<wbr>At</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of identity that last modified the resource.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="lastmodifiedby_go">
<a href="#lastmodifiedby_go" style="color: inherit; text-decoration: inherit;">Last<wbr>Modified<wbr>By</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The identity that last modified the resource.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="lastmodifiedbytype_go">
<a href="#lastmodifiedbytype_go" style="color: inherit; text-decoration: inherit;">Last<wbr>Modified<wbr>By<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of identity that last modified the resource.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="createdat_nodejs">
<a href="#createdat_nodejs" style="color: inherit; text-decoration: inherit;">created<wbr>At</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The timestamp of resource creation (UTC).{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="createdby_nodejs">
<a href="#createdby_nodejs" style="color: inherit; text-decoration: inherit;">created<wbr>By</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The identity that created the resource.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="createdbytype_nodejs">
<a href="#createdbytype_nodejs" style="color: inherit; text-decoration: inherit;">created<wbr>By<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of identity that created the resource.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="lastmodifiedat_nodejs">
<a href="#lastmodifiedat_nodejs" style="color: inherit; text-decoration: inherit;">last<wbr>Modified<wbr>At</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of identity that last modified the resource.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="lastmodifiedby_nodejs">
<a href="#lastmodifiedby_nodejs" style="color: inherit; text-decoration: inherit;">last<wbr>Modified<wbr>By</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The identity that last modified the resource.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="lastmodifiedbytype_nodejs">
<a href="#lastmodifiedbytype_nodejs" style="color: inherit; text-decoration: inherit;">last<wbr>Modified<wbr>By<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of identity that last modified the resource.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="created_at_python">
<a href="#created_at_python" style="color: inherit; text-decoration: inherit;">created_<wbr>at</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The timestamp of resource creation (UTC).{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="created_by_python">
<a href="#created_by_python" style="color: inherit; text-decoration: inherit;">created_<wbr>by</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The identity that created the resource.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="created_by_type_python">
<a href="#created_by_type_python" style="color: inherit; text-decoration: inherit;">created_<wbr>by_<wbr>type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of identity that created the resource.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="last_modified_at_python">
<a href="#last_modified_at_python" style="color: inherit; text-decoration: inherit;">last_<wbr>modified_<wbr>at</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of identity that last modified the resource.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="last_modified_by_python">
<a href="#last_modified_by_python" style="color: inherit; text-decoration: inherit;">last_<wbr>modified_<wbr>by</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The identity that last modified the resource.{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="last_modified_by_type_python">
<a href="#last_modified_by_type_python" style="color: inherit; text-decoration: inherit;">last_<wbr>modified_<wbr>by_<wbr>type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of identity that last modified the resource.{{% /md %}}</dd></dl>
{{% /choosable %}}

<h4 id="triggerkind">Trigger<wbr>Kind</h4>

{{% choosable language csharp %}}
<dl class="tabular"><dt>Schedule<wbr>Based</dt>
    <dd>ScheduleBased</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="tabular"><dt>Trigger<wbr>Kind<wbr>Schedule<wbr>Based</dt>
    <dd>ScheduleBased</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="tabular"><dt>Schedule<wbr>Based</dt>
    <dd>ScheduleBased</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="tabular"><dt>SCHEDULE_BASED</dt>
    <dd>ScheduleBased</dd></dl>
{{% /choosable %}}
## Import


An existing resource can be imported using its type token, name, and identifier, e.g.

```sh
$ pulumi import azure-native:datashare:Trigger Trigger1 /subscriptions/433a8dfd-e5d5-4e77-ad86-90acdc75eb1a/resourceGroups/SampleResourceGroup/providers/Microsoft.DataShare/accounts/Account1/shareSubscriptions/ShareSubscription1/triggers/Trigger1 
```




<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-azure-native">https://github.com/pulumi/pulumi-azure-native</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
</dl>
