
---
title: "getGlobalRole"
title_tag: "rancher2.getGlobalRole"
meta_desc: "Documentation for the rancher2.getGlobalRole function with examples, input properties, output properties, and supporting types."
layout: api
no_edit_this_page: true
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Use this data source to retrieve information about a Rancher v2 global role resource.


{{% examples %}}

## Example Usage

{{< chooser language "typescript,python,go,csharp" / >}}





{{< example csharp >}}

```csharp
using Pulumi;
using Rancher2 = Pulumi.Rancher2;

class MyStack : Stack
{
    public MyStack()
    {
        var foo = Output.Create(Rancher2.GetGlobalRole.InvokeAsync(new Rancher2.GetGlobalRoleArgs
        {
            Name = "foo",
        }));
    }

}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-rancher2/sdk/v3/go/rancher2"
	"github.com/pulumi/pulumi/sdk/v3/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		_, err := rancher2.LookupGlobalRole(ctx, &rancher2.LookupGlobalRoleArgs{
			Name: "foo",
		}, nil)
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
import pulumi_rancher2 as rancher2

foo = rancher2.get_global_role(name="foo")
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as rancher2 from "@pulumi/rancher2";

const foo = pulumi.output(rancher2.getGlobalRole({
    name: "foo",
}, { async: true }));
```


{{< /example >}}





{{% /examples %}}




## Using getGlobalRole {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getGlobalRole<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetGlobalRoleArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetGlobalRoleResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_global_role(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                    <span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetGlobalRoleResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupGlobalRole<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">,</span> <span class="nx">args</span><span class="p"> *</span><span class="nx">LookupGlobalRoleArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">LookupGlobalRoleResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `LookupGlobalRole` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetGlobalRole </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetGlobalRoleResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetGlobalRoleArgs</span><span class="p"> </span><span class="nx">args<span class="p">,</span> <span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
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
    <dd>{{% md %}}The name of the Global Role (string)
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
    <dd>{{% md %}}The name of the Global Role (string)
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
    <dd>{{% md %}}The name of the Global Role (string)
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
    <dd>{{% md %}}The name of the Global Role (string)
{{% /md %}}</dd></dl>
{{% /choosable %}}




## getGlobalRole Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="annotations_csharp">
<a href="#annotations_csharp" style="color: inherit; text-decoration: inherit;">Annotations</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Dictionary&lt;string, object&gt;</span>
    </dt>
    <dd>{{% md %}}(Computed) Annotations for global role object (map)
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="builtin_csharp">
<a href="#builtin_csharp" style="color: inherit; text-decoration: inherit;">Builtin</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}(Computed) Builtin global role (bool)
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="description_csharp">
<a href="#description_csharp" style="color: inherit; text-decoration: inherit;">Description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}(Computed) Global role description (string)
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
        <span id="labels_csharp">
<a href="#labels_csharp" style="color: inherit; text-decoration: inherit;">Labels</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Dictionary&lt;string, object&gt;</span>
    </dt>
    <dd>{{% md %}}(Computed) Labels for global role object (map)
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
        <span id="newuserdefault_csharp">
<a href="#newuserdefault_csharp" style="color: inherit; text-decoration: inherit;">New<wbr>User<wbr>Default</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}(Computed) Whether or not this role should be added to new users (bool)
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="rules_csharp">
<a href="#rules_csharp" style="color: inherit; text-decoration: inherit;">Rules</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getglobalrolerule">List&lt;Get<wbr>Global<wbr>Role<wbr>Rule&gt;</a></span>
    </dt>
    <dd>{{% md %}}(Computed) Global role policy rules (list)
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="annotations_go">
<a href="#annotations_go" style="color: inherit; text-decoration: inherit;">Annotations</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}(Computed) Annotations for global role object (map)
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="builtin_go">
<a href="#builtin_go" style="color: inherit; text-decoration: inherit;">Builtin</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}(Computed) Builtin global role (bool)
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="description_go">
<a href="#description_go" style="color: inherit; text-decoration: inherit;">Description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}(Computed) Global role description (string)
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
        <span id="labels_go">
<a href="#labels_go" style="color: inherit; text-decoration: inherit;">Labels</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}(Computed) Labels for global role object (map)
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
        <span id="newuserdefault_go">
<a href="#newuserdefault_go" style="color: inherit; text-decoration: inherit;">New<wbr>User<wbr>Default</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}(Computed) Whether or not this role should be added to new users (bool)
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="rules_go">
<a href="#rules_go" style="color: inherit; text-decoration: inherit;">Rules</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getglobalrolerule">[]Get<wbr>Global<wbr>Role<wbr>Rule</a></span>
    </dt>
    <dd>{{% md %}}(Computed) Global role policy rules (list)
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="annotations_nodejs">
<a href="#annotations_nodejs" style="color: inherit; text-decoration: inherit;">annotations</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}</span>
    </dt>
    <dd>{{% md %}}(Computed) Annotations for global role object (map)
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="builtin_nodejs">
<a href="#builtin_nodejs" style="color: inherit; text-decoration: inherit;">builtin</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}(Computed) Builtin global role (bool)
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="description_nodejs">
<a href="#description_nodejs" style="color: inherit; text-decoration: inherit;">description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}(Computed) Global role description (string)
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
        <span id="labels_nodejs">
<a href="#labels_nodejs" style="color: inherit; text-decoration: inherit;">labels</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}</span>
    </dt>
    <dd>{{% md %}}(Computed) Labels for global role object (map)
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
        <span id="newuserdefault_nodejs">
<a href="#newuserdefault_nodejs" style="color: inherit; text-decoration: inherit;">new<wbr>User<wbr>Default</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}(Computed) Whether or not this role should be added to new users (bool)
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="rules_nodejs">
<a href="#rules_nodejs" style="color: inherit; text-decoration: inherit;">rules</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getglobalrolerule">Get<wbr>Global<wbr>Role<wbr>Rule[]</a></span>
    </dt>
    <dd>{{% md %}}(Computed) Global role policy rules (list)
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="annotations_python">
<a href="#annotations_python" style="color: inherit; text-decoration: inherit;">annotations</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Mapping[str, Any]</span>
    </dt>
    <dd>{{% md %}}(Computed) Annotations for global role object (map)
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="builtin_python">
<a href="#builtin_python" style="color: inherit; text-decoration: inherit;">builtin</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}(Computed) Builtin global role (bool)
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="description_python">
<a href="#description_python" style="color: inherit; text-decoration: inherit;">description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}(Computed) Global role description (string)
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
        <span id="labels_python">
<a href="#labels_python" style="color: inherit; text-decoration: inherit;">labels</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Mapping[str, Any]</span>
    </dt>
    <dd>{{% md %}}(Computed) Labels for global role object (map)
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
        <span id="new_user_default_python">
<a href="#new_user_default_python" style="color: inherit; text-decoration: inherit;">new_<wbr>user_<wbr>default</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}(Computed) Whether or not this role should be added to new users (bool)
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="rules_python">
<a href="#rules_python" style="color: inherit; text-decoration: inherit;">rules</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getglobalrolerule">Sequence[Get<wbr>Global<wbr>Role<wbr>Rule]</a></span>
    </dt>
    <dd>{{% md %}}(Computed) Global role policy rules (list)
{{% /md %}}</dd></dl>
{{% /choosable %}}




## Supporting Types


<h4 id="getglobalrolerule">Get<wbr>Global<wbr>Role<wbr>Rule</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="apigroups_csharp">
<a href="#apigroups_csharp" style="color: inherit; text-decoration: inherit;">Api<wbr>Groups</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="nonresourceurls_csharp">
<a href="#nonresourceurls_csharp" style="color: inherit; text-decoration: inherit;">Non<wbr>Resource<wbr>Urls</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="resourcenames_csharp">
<a href="#resourcenames_csharp" style="color: inherit; text-decoration: inherit;">Resource<wbr>Names</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="resources_csharp">
<a href="#resources_csharp" style="color: inherit; text-decoration: inherit;">Resources</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="verbs_csharp">
<a href="#verbs_csharp" style="color: inherit; text-decoration: inherit;">Verbs</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="apigroups_go">
<a href="#apigroups_go" style="color: inherit; text-decoration: inherit;">Api<wbr>Groups</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="nonresourceurls_go">
<a href="#nonresourceurls_go" style="color: inherit; text-decoration: inherit;">Non<wbr>Resource<wbr>Urls</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="resourcenames_go">
<a href="#resourcenames_go" style="color: inherit; text-decoration: inherit;">Resource<wbr>Names</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="resources_go">
<a href="#resources_go" style="color: inherit; text-decoration: inherit;">Resources</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="verbs_go">
<a href="#verbs_go" style="color: inherit; text-decoration: inherit;">Verbs</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="apigroups_nodejs">
<a href="#apigroups_nodejs" style="color: inherit; text-decoration: inherit;">api<wbr>Groups</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="nonresourceurls_nodejs">
<a href="#nonresourceurls_nodejs" style="color: inherit; text-decoration: inherit;">non<wbr>Resource<wbr>Urls</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="resourcenames_nodejs">
<a href="#resourcenames_nodejs" style="color: inherit; text-decoration: inherit;">resource<wbr>Names</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="resources_nodejs">
<a href="#resources_nodejs" style="color: inherit; text-decoration: inherit;">resources</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="verbs_nodejs">
<a href="#verbs_nodejs" style="color: inherit; text-decoration: inherit;">verbs</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="api_groups_python">
<a href="#api_groups_python" style="color: inherit; text-decoration: inherit;">api_<wbr>groups</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="non_resource_urls_python">
<a href="#non_resource_urls_python" style="color: inherit; text-decoration: inherit;">non_<wbr>resource_<wbr>urls</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="resource_names_python">
<a href="#resource_names_python" style="color: inherit; text-decoration: inherit;">resource_<wbr>names</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="resources_python">
<a href="#resources_python" style="color: inherit; text-decoration: inherit;">resources</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="verbs_python">
<a href="#verbs_python" style="color: inherit; text-decoration: inherit;">verbs</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-rancher2">https://github.com/pulumi/pulumi-rancher2</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`rancher2` Terraform Provider](https://github.com/rancher/terraform-provider-rancher2).{{% /md %}}</dd>
</dl>
