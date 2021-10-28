
---
title: "getAccounts"
title_tag: "alicloud.polardb.getAccounts"
meta_desc: "Documentation for the alicloud.polardb.getAccounts function with examples, input properties, output properties, and supporting types."
layout: api
no_edit_this_page: true
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

The `alicloud.polardb.getAccounts` data source provides a collection of PolarDB cluster database account available in Alibaba Cloud account.
Filters support regular expression for the account name, searches by clusterId.

> **NOTE:** Available in v1.70.0+.


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
        var polardbClustersDs = Output.Create(AliCloud.PolarDB.GetClusters.InvokeAsync(new AliCloud.PolarDB.GetClustersArgs
        {
            DescriptionRegex = "pc-\\w+",
            Status = "Running",
        }));
        var @default = polardbClustersDs.Apply(polardbClustersDs => Output.Create(AliCloud.PolarDB.GetAccounts.InvokeAsync(new AliCloud.PolarDB.GetAccountsArgs
        {
            DbClusterId = polardbClustersDs.Clusters[0].Id,
        })));
        this.Account = @default.Apply(@default => @default.Accounts[0].AccountName);
    }

    [Output("account")]
    public Output<string> Account { get; set; }
}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-alicloud/sdk/v3/go/alicloud/polardb"
	"github.com/pulumi/pulumi/sdk/v3/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		opt0 := "pc-\\w+"
		opt1 := "Running"
		polardbClustersDs, err := polardb.GetClusters(ctx, &polardb.GetClustersArgs{
			DescriptionRegex: &opt0,
			Status:           &opt1,
		}, nil)
		if err != nil {
			return err
		}
		_default, err := polardb.GetAccounts(ctx, &polardb.GetAccountsArgs{
			DbClusterId: polardbClustersDs.Clusters[0].Id,
		}, nil)
		if err != nil {
			return err
		}
		ctx.Export("account", _default.Accounts[0].AccountName)
		return nil
	})
}
```


{{< /example >}}


{{< example python >}}

```python
import pulumi
import pulumi_alicloud as alicloud

polardb_clusters_ds = alicloud.polardb.get_clusters(description_regex="pc-\\w+",
    status="Running")
default = alicloud.polardb.get_accounts(db_cluster_id=polardb_clusters_ds.clusters[0].id)
pulumi.export("account", default.accounts[0].account_name)
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as alicloud from "@pulumi/alicloud";

const polardbClustersDs = alicloud.polardb.getClusters({
    descriptionRegex: "pc-\\w+",
    status: "Running",
});
const default = polardbClustersDs.then(polardbClustersDs => alicloud.polardb.getAccounts({
    dbClusterId: polardbClustersDs.clusters[0].id,
}));
export const account = _default.then(_default => _default.accounts[0].accountName);
```


{{< /example >}}





{{% /examples %}}




## Using getAccounts {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getAccounts<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetAccountsArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetAccountsResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_accounts(</span><span class="nx">db_cluster_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                 <span class="nx">name_regex</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                 <span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetAccountsResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetAccounts<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">,</span> <span class="nx">args</span><span class="p"> *</span><span class="nx">GetAccountsArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">GetAccountsResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `GetAccounts` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetAccounts </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetAccountsResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetAccountsArgs</span><span class="p"> </span><span class="nx">args<span class="p">,</span> <span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="dbclusterid_csharp">
<a href="#dbclusterid_csharp" style="color: inherit; text-decoration: inherit;">Db<wbr>Cluster<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The polarDB cluster ID.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="nameregex_csharp">
<a href="#nameregex_csharp" style="color: inherit; text-decoration: inherit;">Name<wbr>Regex</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A regex string to filter results by account name.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="dbclusterid_go">
<a href="#dbclusterid_go" style="color: inherit; text-decoration: inherit;">Db<wbr>Cluster<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The polarDB cluster ID.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="nameregex_go">
<a href="#nameregex_go" style="color: inherit; text-decoration: inherit;">Name<wbr>Regex</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A regex string to filter results by account name.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="dbclusterid_nodejs">
<a href="#dbclusterid_nodejs" style="color: inherit; text-decoration: inherit;">db<wbr>Cluster<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The polarDB cluster ID.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="nameregex_nodejs">
<a href="#nameregex_nodejs" style="color: inherit; text-decoration: inherit;">name<wbr>Regex</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A regex string to filter results by account name.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="db_cluster_id_python">
<a href="#db_cluster_id_python" style="color: inherit; text-decoration: inherit;">db_<wbr>cluster_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The polarDB cluster ID.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="name_regex_python">
<a href="#name_regex_python" style="color: inherit; text-decoration: inherit;">name_<wbr>regex</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A regex string to filter results by account name.
{{% /md %}}</dd></dl>
{{% /choosable %}}




## getAccounts Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="accounts_csharp">
<a href="#accounts_csharp" style="color: inherit; text-decoration: inherit;">Accounts</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getaccountsaccount">List&lt;Pulumi.<wbr>Ali<wbr>Cloud.<wbr>Polar<wbr>DB.<wbr>Outputs.<wbr>Get<wbr>Accounts<wbr>Account&gt;</a></span>
    </dt>
    <dd>{{% md %}}A list of PolarDB cluster accounts. Each element contains the following attributes:
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="dbclusterid_csharp">
<a href="#dbclusterid_csharp" style="color: inherit; text-decoration: inherit;">Db<wbr>Cluster<wbr>Id</a>
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
        <span id="names_csharp">
<a href="#names_csharp" style="color: inherit; text-decoration: inherit;">Names</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}Account name of the cluster.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="nameregex_csharp">
<a href="#nameregex_csharp" style="color: inherit; text-decoration: inherit;">Name<wbr>Regex</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="accounts_go">
<a href="#accounts_go" style="color: inherit; text-decoration: inherit;">Accounts</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getaccountsaccount">[]Get<wbr>Accounts<wbr>Account</a></span>
    </dt>
    <dd>{{% md %}}A list of PolarDB cluster accounts. Each element contains the following attributes:
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="dbclusterid_go">
<a href="#dbclusterid_go" style="color: inherit; text-decoration: inherit;">Db<wbr>Cluster<wbr>Id</a>
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
        <span id="names_go">
<a href="#names_go" style="color: inherit; text-decoration: inherit;">Names</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Account name of the cluster.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="nameregex_go">
<a href="#nameregex_go" style="color: inherit; text-decoration: inherit;">Name<wbr>Regex</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="accounts_nodejs">
<a href="#accounts_nodejs" style="color: inherit; text-decoration: inherit;">accounts</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getaccountsaccount">Get<wbr>Accounts<wbr>Account[]</a></span>
    </dt>
    <dd>{{% md %}}A list of PolarDB cluster accounts. Each element contains the following attributes:
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="dbclusterid_nodejs">
<a href="#dbclusterid_nodejs" style="color: inherit; text-decoration: inherit;">db<wbr>Cluster<wbr>Id</a>
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
        <span id="names_nodejs">
<a href="#names_nodejs" style="color: inherit; text-decoration: inherit;">names</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}Account name of the cluster.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="nameregex_nodejs">
<a href="#nameregex_nodejs" style="color: inherit; text-decoration: inherit;">name<wbr>Regex</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="accounts_python">
<a href="#accounts_python" style="color: inherit; text-decoration: inherit;">accounts</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getaccountsaccount">Sequence[Get<wbr>Accounts<wbr>Account]</a></span>
    </dt>
    <dd>{{% md %}}A list of PolarDB cluster accounts. Each element contains the following attributes:
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="db_cluster_id_python">
<a href="#db_cluster_id_python" style="color: inherit; text-decoration: inherit;">db_<wbr>cluster_<wbr>id</a>
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
        <span id="names_python">
<a href="#names_python" style="color: inherit; text-decoration: inherit;">names</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}Account name of the cluster.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_regex_python">
<a href="#name_regex_python" style="color: inherit; text-decoration: inherit;">name_<wbr>regex</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}




## Supporting Types


<h4 id="getaccountsaccount">Get<wbr>Accounts<wbr>Account</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="accountdescription_csharp">
<a href="#accountdescription_csharp" style="color: inherit; text-decoration: inherit;">Account<wbr>Description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Account description.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="accountlockstate_csharp">
<a href="#accountlockstate_csharp" style="color: inherit; text-decoration: inherit;">Account<wbr>Lock<wbr>State</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Account lock state, Valid values are `Lock`, `UnLock`.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="accountname_csharp">
<a href="#accountname_csharp" style="color: inherit; text-decoration: inherit;">Account<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Account name.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="accountstatus_csharp">
<a href="#accountstatus_csharp" style="color: inherit; text-decoration: inherit;">Account<wbr>Status</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Cluster address type.`Cluster`: the default address of the Cluster.`Primary`: Primary address.`Custom`: Custom cluster addresses.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="accounttype_csharp">
<a href="#accounttype_csharp" style="color: inherit; text-decoration: inherit;">Account<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Account type, Valid values are `Normal`, `Super`.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="databaseprivileges_csharp">
<a href="#databaseprivileges_csharp" style="color: inherit; text-decoration: inherit;">Database<wbr>Privileges</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getaccountsaccountdatabaseprivilege">List&lt;Pulumi.<wbr>Ali<wbr>Cloud.<wbr>Polar<wbr>DB.<wbr>Inputs.<wbr>Get<wbr>Accounts<wbr>Account<wbr>Database<wbr>Privilege&gt;</a></span>
    </dt>
    <dd>{{% md %}}A list of database privilege. Each element contains the following attributes.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="accountdescription_go">
<a href="#accountdescription_go" style="color: inherit; text-decoration: inherit;">Account<wbr>Description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Account description.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="accountlockstate_go">
<a href="#accountlockstate_go" style="color: inherit; text-decoration: inherit;">Account<wbr>Lock<wbr>State</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Account lock state, Valid values are `Lock`, `UnLock`.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="accountname_go">
<a href="#accountname_go" style="color: inherit; text-decoration: inherit;">Account<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Account name.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="accountstatus_go">
<a href="#accountstatus_go" style="color: inherit; text-decoration: inherit;">Account<wbr>Status</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Cluster address type.`Cluster`: the default address of the Cluster.`Primary`: Primary address.`Custom`: Custom cluster addresses.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="accounttype_go">
<a href="#accounttype_go" style="color: inherit; text-decoration: inherit;">Account<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Account type, Valid values are `Normal`, `Super`.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="databaseprivileges_go">
<a href="#databaseprivileges_go" style="color: inherit; text-decoration: inherit;">Database<wbr>Privileges</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getaccountsaccountdatabaseprivilege">[]Get<wbr>Accounts<wbr>Account<wbr>Database<wbr>Privilege</a></span>
    </dt>
    <dd>{{% md %}}A list of database privilege. Each element contains the following attributes.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="accountdescription_nodejs">
<a href="#accountdescription_nodejs" style="color: inherit; text-decoration: inherit;">account<wbr>Description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Account description.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="accountlockstate_nodejs">
<a href="#accountlockstate_nodejs" style="color: inherit; text-decoration: inherit;">account<wbr>Lock<wbr>State</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Account lock state, Valid values are `Lock`, `UnLock`.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="accountname_nodejs">
<a href="#accountname_nodejs" style="color: inherit; text-decoration: inherit;">account<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Account name.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="accountstatus_nodejs">
<a href="#accountstatus_nodejs" style="color: inherit; text-decoration: inherit;">account<wbr>Status</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Cluster address type.`Cluster`: the default address of the Cluster.`Primary`: Primary address.`Custom`: Custom cluster addresses.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="accounttype_nodejs">
<a href="#accounttype_nodejs" style="color: inherit; text-decoration: inherit;">account<wbr>Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Account type, Valid values are `Normal`, `Super`.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="databaseprivileges_nodejs">
<a href="#databaseprivileges_nodejs" style="color: inherit; text-decoration: inherit;">database<wbr>Privileges</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getaccountsaccountdatabaseprivilege">Get<wbr>Accounts<wbr>Account<wbr>Database<wbr>Privilege[]</a></span>
    </dt>
    <dd>{{% md %}}A list of database privilege. Each element contains the following attributes.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="account_description_python">
<a href="#account_description_python" style="color: inherit; text-decoration: inherit;">account_<wbr>description</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Account description.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="account_lock_state_python">
<a href="#account_lock_state_python" style="color: inherit; text-decoration: inherit;">account_<wbr>lock_<wbr>state</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Account lock state, Valid values are `Lock`, `UnLock`.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="account_name_python">
<a href="#account_name_python" style="color: inherit; text-decoration: inherit;">account_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Account name.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="account_status_python">
<a href="#account_status_python" style="color: inherit; text-decoration: inherit;">account_<wbr>status</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Cluster address type.`Cluster`: the default address of the Cluster.`Primary`: Primary address.`Custom`: Custom cluster addresses.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="account_type_python">
<a href="#account_type_python" style="color: inherit; text-decoration: inherit;">account_<wbr>type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Account type, Valid values are `Normal`, `Super`.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="database_privileges_python">
<a href="#database_privileges_python" style="color: inherit; text-decoration: inherit;">database_<wbr>privileges</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getaccountsaccountdatabaseprivilege">Sequence[Get<wbr>Accounts<wbr>Account<wbr>Database<wbr>Privilege]</a></span>
    </dt>
    <dd>{{% md %}}A list of database privilege. Each element contains the following attributes.
{{% /md %}}</dd></dl>
{{% /choosable %}}

<h4 id="getaccountsaccountdatabaseprivilege">Get<wbr>Accounts<wbr>Account<wbr>Database<wbr>Privilege</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="accountprivilege_csharp">
<a href="#accountprivilege_csharp" style="color: inherit; text-decoration: inherit;">Account<wbr>Privilege</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Account privilege of database
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="dbname_csharp">
<a href="#dbname_csharp" style="color: inherit; text-decoration: inherit;">Db<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The account owned database name
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="accountprivilege_go">
<a href="#accountprivilege_go" style="color: inherit; text-decoration: inherit;">Account<wbr>Privilege</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Account privilege of database
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="dbname_go">
<a href="#dbname_go" style="color: inherit; text-decoration: inherit;">Db<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The account owned database name
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="accountprivilege_nodejs">
<a href="#accountprivilege_nodejs" style="color: inherit; text-decoration: inherit;">account<wbr>Privilege</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Account privilege of database
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="dbname_nodejs">
<a href="#dbname_nodejs" style="color: inherit; text-decoration: inherit;">db<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The account owned database name
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="account_privilege_python">
<a href="#account_privilege_python" style="color: inherit; text-decoration: inherit;">account_<wbr>privilege</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Account privilege of database
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="db_name_python">
<a href="#db_name_python" style="color: inherit; text-decoration: inherit;">db_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The account owned database name
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
