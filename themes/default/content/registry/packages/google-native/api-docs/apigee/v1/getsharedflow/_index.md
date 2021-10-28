
---
title: "getSharedflow"
title_tag: "google-native.apigee/v1.getSharedflow"
meta_desc: "Documentation for the google-native.apigee/v1.getSharedflow function with examples, input properties, output properties, and supporting types."
layout: api
no_edit_this_page: true
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Gets a shared flow by name, including a list of its revisions.




## Using getSharedflow {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getSharedflow<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetSharedflowArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetSharedflowResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_sharedflow(</span><span class="nx">organization_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                   <span class="nx">sharedflow_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                   <span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetSharedflowResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupSharedflow<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">,</span> <span class="nx">args</span><span class="p"> *</span><span class="nx">LookupSharedflowArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">LookupSharedflowResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `LookupSharedflow` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetSharedflow </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetSharedflowResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetSharedflowArgs</span><span class="p"> </span><span class="nx">args<span class="p">,</span> <span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="organizationid_csharp">
<a href="#organizationid_csharp" style="color: inherit; text-decoration: inherit;">Organization<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="sharedflowid_csharp">
<a href="#sharedflowid_csharp" style="color: inherit; text-decoration: inherit;">Sharedflow<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="organizationid_go">
<a href="#organizationid_go" style="color: inherit; text-decoration: inherit;">Organization<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="sharedflowid_go">
<a href="#sharedflowid_go" style="color: inherit; text-decoration: inherit;">Sharedflow<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="organizationid_nodejs">
<a href="#organizationid_nodejs" style="color: inherit; text-decoration: inherit;">organization<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="sharedflowid_nodejs">
<a href="#sharedflowid_nodejs" style="color: inherit; text-decoration: inherit;">sharedflow<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="organization_id_python">
<a href="#organization_id_python" style="color: inherit; text-decoration: inherit;">organization_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="sharedflow_id_python">
<a href="#sharedflow_id_python" style="color: inherit; text-decoration: inherit;">sharedflow_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}




## getSharedflow Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="latestrevisionid_csharp">
<a href="#latestrevisionid_csharp" style="color: inherit; text-decoration: inherit;">Latest<wbr>Revision<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the most recently created revision for this shared flow.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="metadata_csharp">
<a href="#metadata_csharp" style="color: inherit; text-decoration: inherit;">Meta<wbr>Data</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#googlecloudapigeev1entitymetadataresponse">Pulumi.<wbr>Google<wbr>Native.<wbr>Apigee.<wbr>V1.<wbr>Outputs.<wbr>Google<wbr>Cloud<wbr>Apigee<wbr>V1Entity<wbr>Metadata<wbr>Response</a></span>
    </dt>
    <dd>{{% md %}}Metadata describing the shared flow.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the shared flow.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="revision_csharp">
<a href="#revision_csharp" style="color: inherit; text-decoration: inherit;">Revision</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}A list of revisions of this shared flow.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="latestrevisionid_go">
<a href="#latestrevisionid_go" style="color: inherit; text-decoration: inherit;">Latest<wbr>Revision<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the most recently created revision for this shared flow.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="metadata_go">
<a href="#metadata_go" style="color: inherit; text-decoration: inherit;">Meta<wbr>Data</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#googlecloudapigeev1entitymetadataresponse">Google<wbr>Cloud<wbr>Apigee<wbr>V1Entity<wbr>Metadata<wbr>Response</a></span>
    </dt>
    <dd>{{% md %}}Metadata describing the shared flow.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_go">
<a href="#name_go" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the shared flow.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="revision_go">
<a href="#revision_go" style="color: inherit; text-decoration: inherit;">Revision</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of revisions of this shared flow.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="latestrevisionid_nodejs">
<a href="#latestrevisionid_nodejs" style="color: inherit; text-decoration: inherit;">latest<wbr>Revision<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the most recently created revision for this shared flow.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="metadata_nodejs">
<a href="#metadata_nodejs" style="color: inherit; text-decoration: inherit;">meta<wbr>Data</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#googlecloudapigeev1entitymetadataresponse">Google<wbr>Cloud<wbr>Apigee<wbr>V1Entity<wbr>Metadata<wbr>Response</a></span>
    </dt>
    <dd>{{% md %}}Metadata describing the shared flow.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_nodejs">
<a href="#name_nodejs" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the shared flow.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="revision_nodejs">
<a href="#revision_nodejs" style="color: inherit; text-decoration: inherit;">revision</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of revisions of this shared flow.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="latest_revision_id_python">
<a href="#latest_revision_id_python" style="color: inherit; text-decoration: inherit;">latest_<wbr>revision_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The id of the most recently created revision for this shared flow.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="meta_data_python">
<a href="#meta_data_python" style="color: inherit; text-decoration: inherit;">meta_<wbr>data</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#googlecloudapigeev1entitymetadataresponse">Google<wbr>Cloud<wbr>Apigee<wbr>V1Entity<wbr>Metadata<wbr>Response</a></span>
    </dt>
    <dd>{{% md %}}Metadata describing the shared flow.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_python">
<a href="#name_python" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the shared flow.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="revision_python">
<a href="#revision_python" style="color: inherit; text-decoration: inherit;">revision</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}A list of revisions of this shared flow.{{% /md %}}</dd></dl>
{{% /choosable %}}




## Supporting Types


<h4 id="googlecloudapigeev1entitymetadataresponse">Google<wbr>Cloud<wbr>Apigee<wbr>V1Entity<wbr>Metadata<wbr>Response</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="createdat_csharp">
<a href="#createdat_csharp" style="color: inherit; text-decoration: inherit;">Created<wbr>At</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Time at which the API proxy was created, in milliseconds since epoch.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="lastmodifiedat_csharp">
<a href="#lastmodifiedat_csharp" style="color: inherit; text-decoration: inherit;">Last<wbr>Modified<wbr>At</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Time at which the API proxy was most recently modified, in milliseconds since epoch.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="subtype_csharp">
<a href="#subtype_csharp" style="color: inherit; text-decoration: inherit;">Sub<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of entity described{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="createdat_go">
<a href="#createdat_go" style="color: inherit; text-decoration: inherit;">Created<wbr>At</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Time at which the API proxy was created, in milliseconds since epoch.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="lastmodifiedat_go">
<a href="#lastmodifiedat_go" style="color: inherit; text-decoration: inherit;">Last<wbr>Modified<wbr>At</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Time at which the API proxy was most recently modified, in milliseconds since epoch.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="subtype_go">
<a href="#subtype_go" style="color: inherit; text-decoration: inherit;">Sub<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of entity described{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="createdat_nodejs">
<a href="#createdat_nodejs" style="color: inherit; text-decoration: inherit;">created<wbr>At</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Time at which the API proxy was created, in milliseconds since epoch.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="lastmodifiedat_nodejs">
<a href="#lastmodifiedat_nodejs" style="color: inherit; text-decoration: inherit;">last<wbr>Modified<wbr>At</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Time at which the API proxy was most recently modified, in milliseconds since epoch.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="subtype_nodejs">
<a href="#subtype_nodejs" style="color: inherit; text-decoration: inherit;">sub<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of entity described{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="created_at_python">
<a href="#created_at_python" style="color: inherit; text-decoration: inherit;">created_<wbr>at</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Time at which the API proxy was created, in milliseconds since epoch.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="last_modified_at_python">
<a href="#last_modified_at_python" style="color: inherit; text-decoration: inherit;">last_<wbr>modified_<wbr>at</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Time at which the API proxy was most recently modified, in milliseconds since epoch.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="sub_type_python">
<a href="#sub_type_python" style="color: inherit; text-decoration: inherit;">sub_<wbr>type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of entity described{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-google-native">https://github.com/pulumi/pulumi-google-native</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
</dl>
