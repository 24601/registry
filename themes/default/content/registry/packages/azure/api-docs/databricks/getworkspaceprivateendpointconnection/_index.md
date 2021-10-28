
---
title: "getWorkspacePrivateEndpointConnection"
title_tag: "azure.databricks.getWorkspacePrivateEndpointConnection"
meta_desc: "Documentation for the azure.databricks.getWorkspacePrivateEndpointConnection function with examples, input properties, output properties, and supporting types."
layout: api
no_edit_this_page: true
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Use this data source to access information on an existing Databricks Workspace private endpoint connection state.


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
        var example = Output.Create(Azure.DataBricks.GetWorkspacePrivateEndpointConnection.InvokeAsync(new Azure.DataBricks.GetWorkspacePrivateEndpointConnectionArgs
        {
            WorkspaceId = azurerm_databricks_workspace.Example.Id,
            PrivateEndpointId = azurerm_private_endpoint.Example.Id,
        }));
        this.DatabricksWorkspacePrivateEndpointConnectionStatus = example.Apply(example => example.Connections?[0]?.Status);
    }

    [Output("databricksWorkspacePrivateEndpointConnectionStatus")]
    public Output<string> DatabricksWorkspacePrivateEndpointConnectionStatus { get; set; }
}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-azure/sdk/v4/go/azure/databricks"
	"github.com/pulumi/pulumi/sdk/v3/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		example, err := databricks.GetWorkspacePrivateEndpointConnection(ctx, &databricks.GetWorkspacePrivateEndpointConnectionArgs{
			WorkspaceId:       azurerm_databricks_workspace.Example.Id,
			PrivateEndpointId: azurerm_private_endpoint.Example.Id,
		}, nil)
		if err != nil {
			return err
		}
		ctx.Export("databricksWorkspacePrivateEndpointConnectionStatus", example.Connections[0].Status)
		return nil
	})
}
```


{{< /example >}}


{{< example python >}}

```python
import pulumi
import pulumi_azure as azure

example = azure.databricks.get_workspace_private_endpoint_connection(workspace_id=azurerm_databricks_workspace["example"]["id"],
    private_endpoint_id=azurerm_private_endpoint["example"]["id"])
pulumi.export("databricksWorkspacePrivateEndpointConnectionStatus", example.connections[0].status)
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as azure from "@pulumi/azure";

const example = azure.databricks.getWorkspacePrivateEndpointConnection({
    workspaceId: azurerm_databricks_workspace.example.id,
    privateEndpointId: azurerm_private_endpoint.example.id,
});
export const databricksWorkspacePrivateEndpointConnectionStatus = example.then(example => example.connections?[0]?.status);
```


{{< /example >}}





{{% /examples %}}




## Using getWorkspacePrivateEndpointConnection {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getWorkspacePrivateEndpointConnection<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetWorkspacePrivateEndpointConnectionArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetWorkspacePrivateEndpointConnectionResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_workspace_private_endpoint_connection(</span><span class="nx">private_endpoint_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                                              <span class="nx">workspace_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                                              <span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetWorkspacePrivateEndpointConnectionResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetWorkspacePrivateEndpointConnection<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">,</span> <span class="nx">args</span><span class="p"> *</span><span class="nx">GetWorkspacePrivateEndpointConnectionArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">GetWorkspacePrivateEndpointConnectionResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `GetWorkspacePrivateEndpointConnection` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetWorkspacePrivateEndpointConnection </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetWorkspacePrivateEndpointConnectionResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetWorkspacePrivateEndpointConnectionArgs</span><span class="p"> </span><span class="nx">args<span class="p">,</span> <span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="privateendpointid_csharp">
<a href="#privateendpointid_csharp" style="color: inherit; text-decoration: inherit;">Private<wbr>Endpoint<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource ID of the Private Endpoint.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="workspaceid_csharp">
<a href="#workspaceid_csharp" style="color: inherit; text-decoration: inherit;">Workspace<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource ID of the Databricks Workspace.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="privateendpointid_go">
<a href="#privateendpointid_go" style="color: inherit; text-decoration: inherit;">Private<wbr>Endpoint<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource ID of the Private Endpoint.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="workspaceid_go">
<a href="#workspaceid_go" style="color: inherit; text-decoration: inherit;">Workspace<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource ID of the Databricks Workspace.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="privateendpointid_nodejs">
<a href="#privateendpointid_nodejs" style="color: inherit; text-decoration: inherit;">private<wbr>Endpoint<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource ID of the Private Endpoint.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="workspaceid_nodejs">
<a href="#workspaceid_nodejs" style="color: inherit; text-decoration: inherit;">workspace<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource ID of the Databricks Workspace.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="private_endpoint_id_python">
<a href="#private_endpoint_id_python" style="color: inherit; text-decoration: inherit;">private_<wbr>endpoint_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The resource ID of the Private Endpoint.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="workspace_id_python">
<a href="#workspace_id_python" style="color: inherit; text-decoration: inherit;">workspace_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The resource ID of the Databricks Workspace.
{{% /md %}}</dd></dl>
{{% /choosable %}}




## getWorkspacePrivateEndpointConnection Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="connections_csharp">
<a href="#connections_csharp" style="color: inherit; text-decoration: inherit;">Connections</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getworkspaceprivateendpointconnectionconnection">List&lt;Get<wbr>Workspace<wbr>Private<wbr>Endpoint<wbr>Connection<wbr>Connection&gt;</a></span>
    </dt>
    <dd>{{% md %}}A `connections` block as documented below.
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
        <span id="privateendpointid_csharp">
<a href="#privateendpointid_csharp" style="color: inherit; text-decoration: inherit;">Private<wbr>Endpoint<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource ID of the Private Endpoint.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="workspaceid_csharp">
<a href="#workspaceid_csharp" style="color: inherit; text-decoration: inherit;">Workspace<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource ID of the Databricks Workspace.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="connections_go">
<a href="#connections_go" style="color: inherit; text-decoration: inherit;">Connections</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getworkspaceprivateendpointconnectionconnection">[]Get<wbr>Workspace<wbr>Private<wbr>Endpoint<wbr>Connection<wbr>Connection</a></span>
    </dt>
    <dd>{{% md %}}A `connections` block as documented below.
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
        <span id="privateendpointid_go">
<a href="#privateendpointid_go" style="color: inherit; text-decoration: inherit;">Private<wbr>Endpoint<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource ID of the Private Endpoint.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="workspaceid_go">
<a href="#workspaceid_go" style="color: inherit; text-decoration: inherit;">Workspace<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource ID of the Databricks Workspace.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="connections_nodejs">
<a href="#connections_nodejs" style="color: inherit; text-decoration: inherit;">connections</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getworkspaceprivateendpointconnectionconnection">Get<wbr>Workspace<wbr>Private<wbr>Endpoint<wbr>Connection<wbr>Connection[]</a></span>
    </dt>
    <dd>{{% md %}}A `connections` block as documented below.
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
        <span id="privateendpointid_nodejs">
<a href="#privateendpointid_nodejs" style="color: inherit; text-decoration: inherit;">private<wbr>Endpoint<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource ID of the Private Endpoint.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="workspaceid_nodejs">
<a href="#workspaceid_nodejs" style="color: inherit; text-decoration: inherit;">workspace<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource ID of the Databricks Workspace.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="connections_python">
<a href="#connections_python" style="color: inherit; text-decoration: inherit;">connections</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getworkspaceprivateendpointconnectionconnection">Sequence[Get<wbr>Workspace<wbr>Private<wbr>Endpoint<wbr>Connection<wbr>Connection]</a></span>
    </dt>
    <dd>{{% md %}}A `connections` block as documented below.
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
        <span id="private_endpoint_id_python">
<a href="#private_endpoint_id_python" style="color: inherit; text-decoration: inherit;">private_<wbr>endpoint_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The resource ID of the Private Endpoint.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="workspace_id_python">
<a href="#workspace_id_python" style="color: inherit; text-decoration: inherit;">workspace_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The resource ID of the Databricks Workspace.
{{% /md %}}</dd></dl>
{{% /choosable %}}




## Supporting Types


<h4 id="getworkspaceprivateendpointconnectionconnection">Get<wbr>Workspace<wbr>Private<wbr>Endpoint<wbr>Connection<wbr>Connection</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="actionrequired_csharp">
<a href="#actionrequired_csharp" style="color: inherit; text-decoration: inherit;">Action<wbr>Required</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Actions required for a private endpoint connection.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="description_csharp">
<a href="#description_csharp" style="color: inherit; text-decoration: inherit;">Description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The description for the current state of a private endpoint connection.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the Databricks Workspace.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="status_csharp">
<a href="#status_csharp" style="color: inherit; text-decoration: inherit;">Status</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The status of a private endpoint connection. Possible values are `Pending`, `Approved`, `Rejected` or `Disconnected`.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="workspaceprivateendpointid_csharp">
<a href="#workspaceprivateendpointid_csharp" style="color: inherit; text-decoration: inherit;">Workspace<wbr>Private<wbr>Endpoint<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Databricks Workspace resource ID for the private link endpoint.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="actionrequired_go">
<a href="#actionrequired_go" style="color: inherit; text-decoration: inherit;">Action<wbr>Required</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Actions required for a private endpoint connection.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="description_go">
<a href="#description_go" style="color: inherit; text-decoration: inherit;">Description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The description for the current state of a private endpoint connection.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="name_go">
<a href="#name_go" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the Databricks Workspace.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="status_go">
<a href="#status_go" style="color: inherit; text-decoration: inherit;">Status</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The status of a private endpoint connection. Possible values are `Pending`, `Approved`, `Rejected` or `Disconnected`.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="workspaceprivateendpointid_go">
<a href="#workspaceprivateendpointid_go" style="color: inherit; text-decoration: inherit;">Workspace<wbr>Private<wbr>Endpoint<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Databricks Workspace resource ID for the private link endpoint.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="actionrequired_nodejs">
<a href="#actionrequired_nodejs" style="color: inherit; text-decoration: inherit;">action<wbr>Required</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Actions required for a private endpoint connection.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="description_nodejs">
<a href="#description_nodejs" style="color: inherit; text-decoration: inherit;">description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The description for the current state of a private endpoint connection.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="name_nodejs">
<a href="#name_nodejs" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the Databricks Workspace.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="status_nodejs">
<a href="#status_nodejs" style="color: inherit; text-decoration: inherit;">status</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The status of a private endpoint connection. Possible values are `Pending`, `Approved`, `Rejected` or `Disconnected`.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="workspaceprivateendpointid_nodejs">
<a href="#workspaceprivateendpointid_nodejs" style="color: inherit; text-decoration: inherit;">workspace<wbr>Private<wbr>Endpoint<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Databricks Workspace resource ID for the private link endpoint.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="action_required_python">
<a href="#action_required_python" style="color: inherit; text-decoration: inherit;">action_<wbr>required</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Actions required for a private endpoint connection.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="description_python">
<a href="#description_python" style="color: inherit; text-decoration: inherit;">description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The description for the current state of a private endpoint connection.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="name_python">
<a href="#name_python" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the Databricks Workspace.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="status_python">
<a href="#status_python" style="color: inherit; text-decoration: inherit;">status</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The status of a private endpoint connection. Possible values are `Pending`, `Approved`, `Rejected` or `Disconnected`.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="workspace_private_endpoint_id_python">
<a href="#workspace_private_endpoint_id_python" style="color: inherit; text-decoration: inherit;">workspace_<wbr>private_<wbr>endpoint_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Databricks Workspace resource ID for the private link endpoint.
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
