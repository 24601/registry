
---
title: "getFolder"
title_tag: "google-native.cloudresourcemanager/v2beta1.getFolder"
meta_desc: "Documentation for the google-native.cloudresourcemanager/v2beta1.getFolder function with examples, input properties, output properties, and supporting types."
layout: api
no_edit_this_page: true
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Retrieves a Folder identified by the supplied resource name. Valid Folder resource names have the format `folders/{folder_id}` (for example, `folders/1234`). The caller must have `resourcemanager.folders.get` permission on the identified folder.




## Using getFolder {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getFolder<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetFolderArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetFolderResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_folder(</span><span class="nx">folder_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
               <span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetFolderResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupFolder<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">,</span> <span class="nx">args</span><span class="p"> *</span><span class="nx">LookupFolderArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">LookupFolderResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `LookupFolder` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetFolder </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetFolderResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetFolderArgs</span><span class="p"> </span><span class="nx">args<span class="p">,</span> <span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="folderid_csharp">
<a href="#folderid_csharp" style="color: inherit; text-decoration: inherit;">Folder<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="folderid_go">
<a href="#folderid_go" style="color: inherit; text-decoration: inherit;">Folder<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="folderid_nodejs">
<a href="#folderid_nodejs" style="color: inherit; text-decoration: inherit;">folder<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="folder_id_python">
<a href="#folder_id_python" style="color: inherit; text-decoration: inherit;">folder_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}




## getFolder Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="createtime_csharp">
<a href="#createtime_csharp" style="color: inherit; text-decoration: inherit;">Create<wbr>Time</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Timestamp when the Folder was created. Assigned by the server.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="displayname_csharp">
<a href="#displayname_csharp" style="color: inherit; text-decoration: inherit;">Display<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The folder's display name. A folder's display name must be unique amongst its siblings, e.g. no two folders with the same parent can share the same display name. The display name must start and end with a letter or digit, may contain letters, digits, spaces, hyphens and underscores and can be no longer than 30 characters. This is captured by the regular expression: `[\p{L}\p{N}]([\p{L}\p{N}_- ]{0,28}[\p{L}\p{N}])?`.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="lifecyclestate_csharp">
<a href="#lifecyclestate_csharp" style="color: inherit; text-decoration: inherit;">Lifecycle<wbr>State</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The lifecycle state of the folder. Updates to the lifecycle_state must be performed via DeleteFolder and UndeleteFolder.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource name of the Folder. Its format is `folders/{folder_id}`, for example: "folders/1234".{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="parent_csharp">
<a href="#parent_csharp" style="color: inherit; text-decoration: inherit;">Parent</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Folder's parent's resource name. Updates to the folder's parent must be performed via MoveFolder.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="createtime_go">
<a href="#createtime_go" style="color: inherit; text-decoration: inherit;">Create<wbr>Time</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Timestamp when the Folder was created. Assigned by the server.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="displayname_go">
<a href="#displayname_go" style="color: inherit; text-decoration: inherit;">Display<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The folder's display name. A folder's display name must be unique amongst its siblings, e.g. no two folders with the same parent can share the same display name. The display name must start and end with a letter or digit, may contain letters, digits, spaces, hyphens and underscores and can be no longer than 30 characters. This is captured by the regular expression: `[\p{L}\p{N}]([\p{L}\p{N}_- ]{0,28}[\p{L}\p{N}])?`.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="lifecyclestate_go">
<a href="#lifecyclestate_go" style="color: inherit; text-decoration: inherit;">Lifecycle<wbr>State</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The lifecycle state of the folder. Updates to the lifecycle_state must be performed via DeleteFolder and UndeleteFolder.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_go">
<a href="#name_go" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource name of the Folder. Its format is `folders/{folder_id}`, for example: "folders/1234".{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="parent_go">
<a href="#parent_go" style="color: inherit; text-decoration: inherit;">Parent</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Folder's parent's resource name. Updates to the folder's parent must be performed via MoveFolder.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="createtime_nodejs">
<a href="#createtime_nodejs" style="color: inherit; text-decoration: inherit;">create<wbr>Time</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Timestamp when the Folder was created. Assigned by the server.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="displayname_nodejs">
<a href="#displayname_nodejs" style="color: inherit; text-decoration: inherit;">display<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The folder's display name. A folder's display name must be unique amongst its siblings, e.g. no two folders with the same parent can share the same display name. The display name must start and end with a letter or digit, may contain letters, digits, spaces, hyphens and underscores and can be no longer than 30 characters. This is captured by the regular expression: `[\p{L}\p{N}]([\p{L}\p{N}_- ]{0,28}[\p{L}\p{N}])?`.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="lifecyclestate_nodejs">
<a href="#lifecyclestate_nodejs" style="color: inherit; text-decoration: inherit;">lifecycle<wbr>State</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The lifecycle state of the folder. Updates to the lifecycle_state must be performed via DeleteFolder and UndeleteFolder.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_nodejs">
<a href="#name_nodejs" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource name of the Folder. Its format is `folders/{folder_id}`, for example: "folders/1234".{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="parent_nodejs">
<a href="#parent_nodejs" style="color: inherit; text-decoration: inherit;">parent</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Folder's parent's resource name. Updates to the folder's parent must be performed via MoveFolder.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="create_time_python">
<a href="#create_time_python" style="color: inherit; text-decoration: inherit;">create_<wbr>time</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Timestamp when the Folder was created. Assigned by the server.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="display_name_python">
<a href="#display_name_python" style="color: inherit; text-decoration: inherit;">display_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The folder's display name. A folder's display name must be unique amongst its siblings, e.g. no two folders with the same parent can share the same display name. The display name must start and end with a letter or digit, may contain letters, digits, spaces, hyphens and underscores and can be no longer than 30 characters. This is captured by the regular expression: `[\p{L}\p{N}]([\p{L}\p{N}_- ]{0,28}[\p{L}\p{N}])?`.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="lifecycle_state_python">
<a href="#lifecycle_state_python" style="color: inherit; text-decoration: inherit;">lifecycle_<wbr>state</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The lifecycle state of the folder. Updates to the lifecycle_state must be performed via DeleteFolder and UndeleteFolder.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_python">
<a href="#name_python" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The resource name of the Folder. Its format is `folders/{folder_id}`, for example: "folders/1234".{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="parent_python">
<a href="#parent_python" style="color: inherit; text-decoration: inherit;">parent</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Folder's parent's resource name. Updates to the folder's parent must be performed via MoveFolder.{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-google-native">https://github.com/pulumi/pulumi-google-native</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
</dl>
