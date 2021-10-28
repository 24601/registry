
---
title: "getSubscription"
title_tag: "azure.core.getSubscription"
meta_desc: "Documentation for the azure.core.getSubscription function with examples, input properties, output properties, and supporting types."
layout: api
no_edit_this_page: true
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Use this data source to access information about an existing Subscription.


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
        var current = Output.Create(Azure.Core.GetSubscription.InvokeAsync());
        this.CurrentSubscriptionDisplayName = current.Apply(current => current.DisplayName);
    }

    [Output("currentSubscriptionDisplayName")]
    public Output<string> CurrentSubscriptionDisplayName { get; set; }
}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-azure/sdk/v4/go/azure/core"
	"github.com/pulumi/pulumi/sdk/v3/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		current, err := core.LookupSubscription(ctx, nil, nil)
		if err != nil {
			return err
		}
		ctx.Export("currentSubscriptionDisplayName", current.DisplayName)
		return nil
	})
}
```


{{< /example >}}


{{< example python >}}

```python
import pulumi
import pulumi_azure as azure

current = azure.core.get_subscription()
pulumi.export("currentSubscriptionDisplayName", current.display_name)
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as azure from "@pulumi/azure";

const current = azure.core.getSubscription({});
export const currentSubscriptionDisplayName = current.then(current => current.displayName);
```


{{< /example >}}





{{% /examples %}}




## Using getSubscription {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getSubscription<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetSubscriptionArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetSubscriptionResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_subscription(</span><span class="nx">subscription_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                     <span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetSubscriptionResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupSubscription<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">,</span> <span class="nx">args</span><span class="p"> *</span><span class="nx">LookupSubscriptionArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">LookupSubscriptionResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `LookupSubscription` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetSubscription </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetSubscriptionResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetSubscriptionArgs</span><span class="p"> </span><span class="nx">args<span class="p">,</span> <span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="subscriptionid_csharp">
<a href="#subscriptionid_csharp" style="color: inherit; text-decoration: inherit;">Subscription<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the ID of the subscription. If this argument is omitted, the subscription ID of the current Azure Resource Manager provider is used.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="subscriptionid_go">
<a href="#subscriptionid_go" style="color: inherit; text-decoration: inherit;">Subscription<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the ID of the subscription. If this argument is omitted, the subscription ID of the current Azure Resource Manager provider is used.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="subscriptionid_nodejs">
<a href="#subscriptionid_nodejs" style="color: inherit; text-decoration: inherit;">subscription<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the ID of the subscription. If this argument is omitted, the subscription ID of the current Azure Resource Manager provider is used.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="subscription_id_python">
<a href="#subscription_id_python" style="color: inherit; text-decoration: inherit;">subscription_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the ID of the subscription. If this argument is omitted, the subscription ID of the current Azure Resource Manager provider is used.
{{% /md %}}</dd></dl>
{{% /choosable %}}




## getSubscription Result {#result}

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
    <dd>{{% md %}}The subscription display name.
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
        <span id="locationplacementid_csharp">
<a href="#locationplacementid_csharp" style="color: inherit; text-decoration: inherit;">Location<wbr>Placement<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The subscription location placement ID.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="quotaid_csharp">
<a href="#quotaid_csharp" style="color: inherit; text-decoration: inherit;">Quota<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The subscription quota ID.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="spendinglimit_csharp">
<a href="#spendinglimit_csharp" style="color: inherit; text-decoration: inherit;">Spending<wbr>Limit</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The subscription spending limit.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="state_csharp">
<a href="#state_csharp" style="color: inherit; text-decoration: inherit;">State</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The subscription state. Possible values are Enabled, Warned, PastDue, Disabled, and Deleted.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="subscriptionid_csharp">
<a href="#subscriptionid_csharp" style="color: inherit; text-decoration: inherit;">Subscription<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The subscription GUID.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="tags_csharp">
<a href="#tags_csharp" style="color: inherit; text-decoration: inherit;">Tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Dictionary&lt;string, string&gt;</span>
    </dt>
    <dd>{{% md %}}A mapping of tags assigned to the Subscription.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="tenantid_csharp">
<a href="#tenantid_csharp" style="color: inherit; text-decoration: inherit;">Tenant<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The subscription tenant ID.
{{% /md %}}</dd></dl>
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
    <dd>{{% md %}}The subscription display name.
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
        <span id="locationplacementid_go">
<a href="#locationplacementid_go" style="color: inherit; text-decoration: inherit;">Location<wbr>Placement<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The subscription location placement ID.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="quotaid_go">
<a href="#quotaid_go" style="color: inherit; text-decoration: inherit;">Quota<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The subscription quota ID.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="spendinglimit_go">
<a href="#spendinglimit_go" style="color: inherit; text-decoration: inherit;">Spending<wbr>Limit</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The subscription spending limit.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="state_go">
<a href="#state_go" style="color: inherit; text-decoration: inherit;">State</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The subscription state. Possible values are Enabled, Warned, PastDue, Disabled, and Deleted.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="subscriptionid_go">
<a href="#subscriptionid_go" style="color: inherit; text-decoration: inherit;">Subscription<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The subscription GUID.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="tags_go">
<a href="#tags_go" style="color: inherit; text-decoration: inherit;">Tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}A mapping of tags assigned to the Subscription.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="tenantid_go">
<a href="#tenantid_go" style="color: inherit; text-decoration: inherit;">Tenant<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The subscription tenant ID.
{{% /md %}}</dd></dl>
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
    <dd>{{% md %}}The subscription display name.
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
        <span id="locationplacementid_nodejs">
<a href="#locationplacementid_nodejs" style="color: inherit; text-decoration: inherit;">location<wbr>Placement<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The subscription location placement ID.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="quotaid_nodejs">
<a href="#quotaid_nodejs" style="color: inherit; text-decoration: inherit;">quota<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The subscription quota ID.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="spendinglimit_nodejs">
<a href="#spendinglimit_nodejs" style="color: inherit; text-decoration: inherit;">spending<wbr>Limit</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The subscription spending limit.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="state_nodejs">
<a href="#state_nodejs" style="color: inherit; text-decoration: inherit;">state</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The subscription state. Possible values are Enabled, Warned, PastDue, Disabled, and Deleted.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="subscriptionid_nodejs">
<a href="#subscriptionid_nodejs" style="color: inherit; text-decoration: inherit;">subscription<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The subscription GUID.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="tags_nodejs">
<a href="#tags_nodejs" style="color: inherit; text-decoration: inherit;">tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags assigned to the Subscription.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="tenantid_nodejs">
<a href="#tenantid_nodejs" style="color: inherit; text-decoration: inherit;">tenant<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The subscription tenant ID.
{{% /md %}}</dd></dl>
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
    <dd>{{% md %}}The subscription display name.
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
        <span id="location_placement_id_python">
<a href="#location_placement_id_python" style="color: inherit; text-decoration: inherit;">location_<wbr>placement_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The subscription location placement ID.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="quota_id_python">
<a href="#quota_id_python" style="color: inherit; text-decoration: inherit;">quota_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The subscription quota ID.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="spending_limit_python">
<a href="#spending_limit_python" style="color: inherit; text-decoration: inherit;">spending_<wbr>limit</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The subscription spending limit.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="state_python">
<a href="#state_python" style="color: inherit; text-decoration: inherit;">state</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The subscription state. Possible values are Enabled, Warned, PastDue, Disabled, and Deleted.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="subscription_id_python">
<a href="#subscription_id_python" style="color: inherit; text-decoration: inherit;">subscription_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The subscription GUID.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="tags_python">
<a href="#tags_python" style="color: inherit; text-decoration: inherit;">tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Mapping[str, str]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags assigned to the Subscription.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="tenant_id_python">
<a href="#tenant_id_python" style="color: inherit; text-decoration: inherit;">tenant_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The subscription tenant ID.
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
