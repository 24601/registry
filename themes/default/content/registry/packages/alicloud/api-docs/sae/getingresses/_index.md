
---
title: "getIngresses"
title_tag: "alicloud.sae.getIngresses"
meta_desc: "Documentation for the alicloud.sae.getIngresses function with examples, input properties, output properties, and supporting types."
layout: api
no_edit_this_page: true
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

This data source provides the Sae Ingresses of the current Alibaba Cloud user.

> **NOTE:** Available in v1.137.0+.




## Using getIngresses {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getIngresses<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetIngressesArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetIngressesResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_ingresses(</span><span class="nx">enable_details</span><span class="p">:</span> <span class="nx">Optional[bool]</span> = None<span class="p">,</span>
                  <span class="nx">ids</span><span class="p">:</span> <span class="nx">Optional[Sequence[str]]</span> = None<span class="p">,</span>
                  <span class="nx">namespace_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                  <span class="nx">output_file</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                  <span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetIngressesResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetIngresses<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">,</span> <span class="nx">args</span><span class="p"> *</span><span class="nx">GetIngressesArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">GetIngressesResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `GetIngresses` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetIngresses </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetIngressesResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetIngressesArgs</span><span class="p"> </span><span class="nx">args<span class="p">,</span> <span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="namespaceid_csharp">
<a href="#namespaceid_csharp" style="color: inherit; text-decoration: inherit;">Namespace<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Id of Namespace.It can contain 2 to 32 characters.The value is in format {RegionId}:{namespace}.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="enabledetails_csharp">
<a href="#enabledetails_csharp" style="color: inherit; text-decoration: inherit;">Enable<wbr>Details</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Default to `false`. Set it to `true` can output more details about resource attributes.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="ids_csharp">
<a href="#ids_csharp" style="color: inherit; text-decoration: inherit;">Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}A list of Ingress IDs.
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
        <span id="namespaceid_go">
<a href="#namespaceid_go" style="color: inherit; text-decoration: inherit;">Namespace<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Id of Namespace.It can contain 2 to 32 characters.The value is in format {RegionId}:{namespace}.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="enabledetails_go">
<a href="#enabledetails_go" style="color: inherit; text-decoration: inherit;">Enable<wbr>Details</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Default to `false`. Set it to `true` can output more details about resource attributes.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="ids_go">
<a href="#ids_go" style="color: inherit; text-decoration: inherit;">Ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of Ingress IDs.
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
        <span id="namespaceid_nodejs">
<a href="#namespaceid_nodejs" style="color: inherit; text-decoration: inherit;">namespace<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Id of Namespace.It can contain 2 to 32 characters.The value is in format {RegionId}:{namespace}.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="enabledetails_nodejs">
<a href="#enabledetails_nodejs" style="color: inherit; text-decoration: inherit;">enable<wbr>Details</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Default to `false`. Set it to `true` can output more details about resource attributes.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="ids_nodejs">
<a href="#ids_nodejs" style="color: inherit; text-decoration: inherit;">ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of Ingress IDs.
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
        <span id="namespace_id_python">
<a href="#namespace_id_python" style="color: inherit; text-decoration: inherit;">namespace_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Id of Namespace.It can contain 2 to 32 characters.The value is in format {RegionId}:{namespace}.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="enable_details_python">
<a href="#enable_details_python" style="color: inherit; text-decoration: inherit;">enable_<wbr>details</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Default to `false`. Set it to `true` can output more details about resource attributes.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="ids_python">
<a href="#ids_python" style="color: inherit; text-decoration: inherit;">ids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}A list of Ingress IDs.
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




## getIngresses Result {#result}

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
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="ingresses_csharp">
<a href="#ingresses_csharp" style="color: inherit; text-decoration: inherit;">Ingresses</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getingressesingress">List&lt;Pulumi.<wbr>Ali<wbr>Cloud.<wbr>Sae.<wbr>Outputs.<wbr>Get<wbr>Ingresses<wbr>Ingress&gt;</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="namespaceid_csharp">
<a href="#namespaceid_csharp" style="color: inherit; text-decoration: inherit;">Namespace<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
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
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="ingresses_go">
<a href="#ingresses_go" style="color: inherit; text-decoration: inherit;">Ingresses</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getingressesingress">[]Get<wbr>Ingresses<wbr>Ingress</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="namespaceid_go">
<a href="#namespaceid_go" style="color: inherit; text-decoration: inherit;">Namespace<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
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
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="ingresses_nodejs">
<a href="#ingresses_nodejs" style="color: inherit; text-decoration: inherit;">ingresses</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getingressesingress">Get<wbr>Ingresses<wbr>Ingress[]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="namespaceid_nodejs">
<a href="#namespaceid_nodejs" style="color: inherit; text-decoration: inherit;">namespace<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
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
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="ingresses_python">
<a href="#ingresses_python" style="color: inherit; text-decoration: inherit;">ingresses</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getingressesingress">Sequence[Get<wbr>Ingresses<wbr>Ingress]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="namespace_id_python">
<a href="#namespace_id_python" style="color: inherit; text-decoration: inherit;">namespace_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
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


<h4 id="getingressesingress">Get<wbr>Ingresses<wbr>Ingress</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="certid_csharp">
<a href="#certid_csharp" style="color: inherit; text-decoration: inherit;">Cert<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Cert Id.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="defaultrule_csharp">
<a href="#defaultrule_csharp" style="color: inherit; text-decoration: inherit;">Default<wbr>Rule</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Default Rule.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="description_csharp">
<a href="#description_csharp" style="color: inherit; text-decoration: inherit;">Description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Description.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="id_csharp">
<a href="#id_csharp" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Ingress.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="ingressid_csharp">
<a href="#ingressid_csharp" style="color: inherit; text-decoration: inherit;">Ingress<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The first ID of the resource.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="listenerport_csharp">
<a href="#listenerport_csharp" style="color: inherit; text-decoration: inherit;">Listener<wbr>Port</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}SLB listening port.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="namespaceid_csharp">
<a href="#namespaceid_csharp" style="color: inherit; text-decoration: inherit;">Namespace<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Id of Namespace.It can contain 2 to 32 characters.The value is in format {RegionId}:{namespace}.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="slbid_csharp">
<a href="#slbid_csharp" style="color: inherit; text-decoration: inherit;">Slb<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}SLB ID.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="certid_go">
<a href="#certid_go" style="color: inherit; text-decoration: inherit;">Cert<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Cert Id.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="defaultrule_go">
<a href="#defaultrule_go" style="color: inherit; text-decoration: inherit;">Default<wbr>Rule</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Default Rule.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="description_go">
<a href="#description_go" style="color: inherit; text-decoration: inherit;">Description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Description.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="id_go">
<a href="#id_go" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Ingress.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="ingressid_go">
<a href="#ingressid_go" style="color: inherit; text-decoration: inherit;">Ingress<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The first ID of the resource.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="listenerport_go">
<a href="#listenerport_go" style="color: inherit; text-decoration: inherit;">Listener<wbr>Port</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}SLB listening port.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="namespaceid_go">
<a href="#namespaceid_go" style="color: inherit; text-decoration: inherit;">Namespace<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Id of Namespace.It can contain 2 to 32 characters.The value is in format {RegionId}:{namespace}.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="slbid_go">
<a href="#slbid_go" style="color: inherit; text-decoration: inherit;">Slb<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}SLB ID.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="certid_nodejs">
<a href="#certid_nodejs" style="color: inherit; text-decoration: inherit;">cert<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Cert Id.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="defaultrule_nodejs">
<a href="#defaultrule_nodejs" style="color: inherit; text-decoration: inherit;">default<wbr>Rule</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Default Rule.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="description_nodejs">
<a href="#description_nodejs" style="color: inherit; text-decoration: inherit;">description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Description.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="id_nodejs">
<a href="#id_nodejs" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Ingress.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="ingressid_nodejs">
<a href="#ingressid_nodejs" style="color: inherit; text-decoration: inherit;">ingress<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The first ID of the resource.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="listenerport_nodejs">
<a href="#listenerport_nodejs" style="color: inherit; text-decoration: inherit;">listener<wbr>Port</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}SLB listening port.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="namespaceid_nodejs">
<a href="#namespaceid_nodejs" style="color: inherit; text-decoration: inherit;">namespace<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Id of Namespace.It can contain 2 to 32 characters.The value is in format {RegionId}:{namespace}.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="slbid_nodejs">
<a href="#slbid_nodejs" style="color: inherit; text-decoration: inherit;">slb<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}SLB ID.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="cert_id_python">
<a href="#cert_id_python" style="color: inherit; text-decoration: inherit;">cert_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Cert Id.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="default_rule_python">
<a href="#default_rule_python" style="color: inherit; text-decoration: inherit;">default_<wbr>rule</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Default Rule.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="description_python">
<a href="#description_python" style="color: inherit; text-decoration: inherit;">description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="id_python">
<a href="#id_python" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the Ingress.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="ingress_id_python">
<a href="#ingress_id_python" style="color: inherit; text-decoration: inherit;">ingress_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The first ID of the resource.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="listener_port_python">
<a href="#listener_port_python" style="color: inherit; text-decoration: inherit;">listener_<wbr>port</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}SLB listening port.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="namespace_id_python">
<a href="#namespace_id_python" style="color: inherit; text-decoration: inherit;">namespace_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Id of Namespace.It can contain 2 to 32 characters.The value is in format {RegionId}:{namespace}.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="slb_id_python">
<a href="#slb_id_python" style="color: inherit; text-decoration: inherit;">slb_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}SLB ID.
{{% /md %}}</dd></dl>
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
