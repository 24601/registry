
---
title: "getPolicyVersions"
title_tag: "alicloud.resourcemanager.getPolicyVersions"
meta_desc: "Documentation for the alicloud.resourcemanager.getPolicyVersions function with examples, input properties, output properties, and supporting types."
layout: api
no_edit_this_page: true
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

This data source provides the Resource Manager Policy Versions of the current Alibaba Cloud user.

> **NOTE:**  Available in 1.85.0+.


{{% examples %}}

## Example Usage

{{< chooser language "typescript,python,go,csharp" / >}}





{{< example csharp >}}

```csharp
using Pulumi;
using AliCloud = Pulumi.AliCloud;

class MyStack : Stack
{
    public MyStack()
    {
        var @default = Output.Create(AliCloud.ResourceManager.GetPolicyVersions.InvokeAsync(new AliCloud.ResourceManager.GetPolicyVersionsArgs
        {
            PolicyName = "tftest",
            PolicyType = "Custom",
        }));
        this.FirstPolicyVersionId = @default.Apply(@default => @default.Versions[0].Id);
    }

    [Output("firstPolicyVersionId")]
    public Output<string> FirstPolicyVersionId { get; set; }
}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-alicloud/sdk/v3/go/alicloud/resourcemanager"
	"github.com/pulumi/pulumi/sdk/v3/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		_default, err := resourcemanager.GetPolicyVersions(ctx, &resourcemanager.GetPolicyVersionsArgs{
			PolicyName: "tftest",
			PolicyType: "Custom",
		}, nil)
		if err != nil {
			return err
		}
		ctx.Export("firstPolicyVersionId", _default.Versions[0].Id)
		return nil
	})
}
```


{{< /example >}}


{{< example python >}}

```python
import pulumi
import pulumi_alicloud as alicloud

default = alicloud.resourcemanager.get_policy_versions(policy_name="tftest",
    policy_type="Custom")
pulumi.export("firstPolicyVersionId", default.versions[0].id)
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as alicloud from "@pulumi/alicloud";

const defaultPolicyVersions = pulumi.output(alicloud.resourcemanager.getPolicyVersions({
    policyName: "tftest",
    policyType: "Custom",
}, { async: true }));

export const firstPolicyVersionId = defaultPolicyVersions.versions[0].id;
```


{{< /example >}}





{{% /examples %}}




## Using getPolicyVersions {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getPolicyVersions<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetPolicyVersionsArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetPolicyVersionsResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_policy_versions(</span><span class="nx">enable_details</span><span class="p">:</span> <span class="nx">Optional[bool]</span> = None<span class="p">,</span>
                        <span class="nx">ids</span><span class="p">:</span> <span class="nx">Optional[Sequence[str]]</span> = None<span class="p">,</span>
                        <span class="nx">output_file</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                        <span class="nx">policy_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                        <span class="nx">policy_type</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                        <span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetPolicyVersionsResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetPolicyVersions<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">,</span> <span class="nx">args</span><span class="p"> *</span><span class="nx">GetPolicyVersionsArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">GetPolicyVersionsResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `GetPolicyVersions` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetPolicyVersions </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetPolicyVersionsResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetPolicyVersionsArgs</span><span class="p"> </span><span class="nx">args<span class="p">,</span> <span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="policyname_csharp">
<a href="#policyname_csharp" style="color: inherit; text-decoration: inherit;">Policy<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the policy.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="policytype_csharp">
<a href="#policytype_csharp" style="color: inherit; text-decoration: inherit;">Policy<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the policy. Valid values:`Custom` and `System`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="enabledetails_csharp">
<a href="#enabledetails_csharp" style="color: inherit; text-decoration: inherit;">Enable<wbr>Details</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}-(Optional, Available in v1.114.0+) Default to `false`. Set it to true can output more details.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="ids_csharp">
<a href="#ids_csharp" style="color: inherit; text-decoration: inherit;">Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}A list of policy version IDs.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="outputfile_csharp">
<a href="#outputfile_csharp" style="color: inherit; text-decoration: inherit;">Output<wbr>File</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="policyname_go">
<a href="#policyname_go" style="color: inherit; text-decoration: inherit;">Policy<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the policy.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="policytype_go">
<a href="#policytype_go" style="color: inherit; text-decoration: inherit;">Policy<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the policy. Valid values:`Custom` and `System`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="enabledetails_go">
<a href="#enabledetails_go" style="color: inherit; text-decoration: inherit;">Enable<wbr>Details</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}-(Optional, Available in v1.114.0+) Default to `false`. Set it to true can output more details.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="ids_go">
<a href="#ids_go" style="color: inherit; text-decoration: inherit;">Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of policy version IDs.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="outputfile_go">
<a href="#outputfile_go" style="color: inherit; text-decoration: inherit;">Output<wbr>File</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="policyname_nodejs">
<a href="#policyname_nodejs" style="color: inherit; text-decoration: inherit;">policy<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the policy.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="policytype_nodejs">
<a href="#policytype_nodejs" style="color: inherit; text-decoration: inherit;">policy<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the policy. Valid values:`Custom` and `System`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="enabledetails_nodejs">
<a href="#enabledetails_nodejs" style="color: inherit; text-decoration: inherit;">enable<wbr>Details</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}-(Optional, Available in v1.114.0+) Default to `false`. Set it to true can output more details.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="ids_nodejs">
<a href="#ids_nodejs" style="color: inherit; text-decoration: inherit;">ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of policy version IDs.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="outputfile_nodejs">
<a href="#outputfile_nodejs" style="color: inherit; text-decoration: inherit;">output<wbr>File</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="policy_name_python">
<a href="#policy_name_python" style="color: inherit; text-decoration: inherit;">policy_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the policy.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="policy_type_python">
<a href="#policy_type_python" style="color: inherit; text-decoration: inherit;">policy_<wbr>type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of the policy. Valid values:`Custom` and `System`.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="enable_details_python">
<a href="#enable_details_python" style="color: inherit; text-decoration: inherit;">enable_<wbr>details</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}-(Optional, Available in v1.114.0+) Default to `false`. Set it to true can output more details.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="ids_python">
<a href="#ids_python" style="color: inherit; text-decoration: inherit;">ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}A list of policy version IDs.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="output_file_python">
<a href="#output_file_python" style="color: inherit; text-decoration: inherit;">output_<wbr>file</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}




## getPolicyVersions Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
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
        <span id="ids_csharp">
<a href="#ids_csharp" style="color: inherit; text-decoration: inherit;">Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}A list of policy version IDs.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="policyname_csharp">
<a href="#policyname_csharp" style="color: inherit; text-decoration: inherit;">Policy<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="policytype_csharp">
<a href="#policytype_csharp" style="color: inherit; text-decoration: inherit;">Policy<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="versions_csharp">
<a href="#versions_csharp" style="color: inherit; text-decoration: inherit;">Versions</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getpolicyversionsversion">List&lt;Pulumi.<wbr>Ali<wbr>Cloud.<wbr>Resource<wbr>Manager.<wbr>Outputs.<wbr>Get<wbr>Policy<wbr>Versions<wbr>Version&gt;</a></span>
    </dt>
    <dd>{{% md %}}A list of policy versions. Each element contains the following attributes:
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="enabledetails_csharp">
<a href="#enabledetails_csharp" style="color: inherit; text-decoration: inherit;">Enable<wbr>Details</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="outputfile_csharp">
<a href="#outputfile_csharp" style="color: inherit; text-decoration: inherit;">Output<wbr>File</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
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
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="ids_go">
<a href="#ids_go" style="color: inherit; text-decoration: inherit;">Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of policy version IDs.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="policyname_go">
<a href="#policyname_go" style="color: inherit; text-decoration: inherit;">Policy<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="policytype_go">
<a href="#policytype_go" style="color: inherit; text-decoration: inherit;">Policy<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="versions_go">
<a href="#versions_go" style="color: inherit; text-decoration: inherit;">Versions</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getpolicyversionsversion">[]Get<wbr>Policy<wbr>Versions<wbr>Version</a></span>
    </dt>
    <dd>{{% md %}}A list of policy versions. Each element contains the following attributes:
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="enabledetails_go">
<a href="#enabledetails_go" style="color: inherit; text-decoration: inherit;">Enable<wbr>Details</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="outputfile_go">
<a href="#outputfile_go" style="color: inherit; text-decoration: inherit;">Output<wbr>File</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
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
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="ids_nodejs">
<a href="#ids_nodejs" style="color: inherit; text-decoration: inherit;">ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of policy version IDs.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="policyname_nodejs">
<a href="#policyname_nodejs" style="color: inherit; text-decoration: inherit;">policy<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="policytype_nodejs">
<a href="#policytype_nodejs" style="color: inherit; text-decoration: inherit;">policy<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="versions_nodejs">
<a href="#versions_nodejs" style="color: inherit; text-decoration: inherit;">versions</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getpolicyversionsversion">Get<wbr>Policy<wbr>Versions<wbr>Version[]</a></span>
    </dt>
    <dd>{{% md %}}A list of policy versions. Each element contains the following attributes:
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="enabledetails_nodejs">
<a href="#enabledetails_nodejs" style="color: inherit; text-decoration: inherit;">enable<wbr>Details</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="outputfile_nodejs">
<a href="#outputfile_nodejs" style="color: inherit; text-decoration: inherit;">output<wbr>File</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
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
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="ids_python">
<a href="#ids_python" style="color: inherit; text-decoration: inherit;">ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}A list of policy version IDs.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="policy_name_python">
<a href="#policy_name_python" style="color: inherit; text-decoration: inherit;">policy_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="policy_type_python">
<a href="#policy_type_python" style="color: inherit; text-decoration: inherit;">policy_<wbr>type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="versions_python">
<a href="#versions_python" style="color: inherit; text-decoration: inherit;">versions</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getpolicyversionsversion">Sequence[Get<wbr>Policy<wbr>Versions<wbr>Version]</a></span>
    </dt>
    <dd>{{% md %}}A list of policy versions. Each element contains the following attributes:
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="enable_details_python">
<a href="#enable_details_python" style="color: inherit; text-decoration: inherit;">enable_<wbr>details</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="output_file_python">
<a href="#output_file_python" style="color: inherit; text-decoration: inherit;">output_<wbr>file</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}




## Supporting Types


<h4 id="getpolicyversionsversion">Get<wbr>Policy<wbr>Versions<wbr>Version</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="id_csharp">
<a href="#id_csharp" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the resource, the value is `<policy_name>`:`<version_id>`.
* `version_id`- The ID of the policy version.
* `create_date`- (Removed form v1.114.0)The time when the policy version was created.
* `is_default_version`- Indicates whether the policy version is the default version.
* `policy_document`- (Available in v1.114.0+) The policy document of the policy version.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="isdefaultversion_csharp">
<a href="#isdefaultversion_csharp" style="color: inherit; text-decoration: inherit;">Is<wbr>Default<wbr>Version</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="policydocument_csharp">
<a href="#policydocument_csharp" style="color: inherit; text-decoration: inherit;">Policy<wbr>Document</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="versionid_csharp">
<a href="#versionid_csharp" style="color: inherit; text-decoration: inherit;">Version<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="id_go">
<a href="#id_go" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the resource, the value is `<policy_name>`:`<version_id>`.
* `version_id`- The ID of the policy version.
* `create_date`- (Removed form v1.114.0)The time when the policy version was created.
* `is_default_version`- Indicates whether the policy version is the default version.
* `policy_document`- (Available in v1.114.0+) The policy document of the policy version.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="isdefaultversion_go">
<a href="#isdefaultversion_go" style="color: inherit; text-decoration: inherit;">Is<wbr>Default<wbr>Version</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="policydocument_go">
<a href="#policydocument_go" style="color: inherit; text-decoration: inherit;">Policy<wbr>Document</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="versionid_go">
<a href="#versionid_go" style="color: inherit; text-decoration: inherit;">Version<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="id_nodejs">
<a href="#id_nodejs" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the resource, the value is `<policy_name>`:`<version_id>`.
* `version_id`- The ID of the policy version.
* `create_date`- (Removed form v1.114.0)The time when the policy version was created.
* `is_default_version`- Indicates whether the policy version is the default version.
* `policy_document`- (Available in v1.114.0+) The policy document of the policy version.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="isdefaultversion_nodejs">
<a href="#isdefaultversion_nodejs" style="color: inherit; text-decoration: inherit;">is<wbr>Default<wbr>Version</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="policydocument_nodejs">
<a href="#policydocument_nodejs" style="color: inherit; text-decoration: inherit;">policy<wbr>Document</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="versionid_nodejs">
<a href="#versionid_nodejs" style="color: inherit; text-decoration: inherit;">version<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="id_python">
<a href="#id_python" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the resource, the value is `<policy_name>`:`<version_id>`.
* `version_id`- The ID of the policy version.
* `create_date`- (Removed form v1.114.0)The time when the policy version was created.
* `is_default_version`- Indicates whether the policy version is the default version.
* `policy_document`- (Available in v1.114.0+) The policy document of the policy version.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="is_default_version_python">
<a href="#is_default_version_python" style="color: inherit; text-decoration: inherit;">is_<wbr>default_<wbr>version</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="policy_document_python">
<a href="#policy_document_python" style="color: inherit; text-decoration: inherit;">policy_<wbr>document</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="version_id_python">
<a href="#version_id_python" style="color: inherit; text-decoration: inherit;">version_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-alicloud">https://github.com/pulumi/pulumi-alicloud</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`alicloud` Terraform Provider](https://github.com/aliyun/terraform-provider-alicloud).{{% /md %}}</dd>
</dl>
