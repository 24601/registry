
---
title: "getConnectionMonitorTest"
title_tag: "azure-native.peering.getConnectionMonitorTest"
meta_desc: "Documentation for the azure-native.peering.getConnectionMonitorTest function with examples, input properties, output properties, and supporting types."
layout: api
no_edit_this_page: true
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

The Connection Monitor Test class.
API Version: 2021-06-01.




## Using getConnectionMonitorTest {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getConnectionMonitorTest<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetConnectionMonitorTestArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetConnectionMonitorTestResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_connection_monitor_test(</span><span class="nx">connection_monitor_test_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                                <span class="nx">peering_service_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                                <span class="nx">resource_group_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                                <span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetConnectionMonitorTestResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupConnectionMonitorTest<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">,</span> <span class="nx">args</span><span class="p"> *</span><span class="nx">LookupConnectionMonitorTestArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">LookupConnectionMonitorTestResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `LookupConnectionMonitorTest` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetConnectionMonitorTest </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetConnectionMonitorTestResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetConnectionMonitorTestArgs</span><span class="p"> </span><span class="nx">args<span class="p">,</span> <span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="connectionmonitortestname_csharp">
<a href="#connectionmonitortestname_csharp" style="color: inherit; text-decoration: inherit;">Connection<wbr>Monitor<wbr>Test<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the connection monitor test{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="peeringservicename_csharp">
<a href="#peeringservicename_csharp" style="color: inherit; text-decoration: inherit;">Peering<wbr>Service<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the peering service.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_csharp">
<a href="#resourcegroupname_csharp" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the resource group.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="connectionmonitortestname_go">
<a href="#connectionmonitortestname_go" style="color: inherit; text-decoration: inherit;">Connection<wbr>Monitor<wbr>Test<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the connection monitor test{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="peeringservicename_go">
<a href="#peeringservicename_go" style="color: inherit; text-decoration: inherit;">Peering<wbr>Service<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the peering service.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_go">
<a href="#resourcegroupname_go" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the resource group.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="connectionmonitortestname_nodejs">
<a href="#connectionmonitortestname_nodejs" style="color: inherit; text-decoration: inherit;">connection<wbr>Monitor<wbr>Test<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the connection monitor test{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="peeringservicename_nodejs">
<a href="#peeringservicename_nodejs" style="color: inherit; text-decoration: inherit;">peering<wbr>Service<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the peering service.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_nodejs">
<a href="#resourcegroupname_nodejs" style="color: inherit; text-decoration: inherit;">resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the resource group.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="connection_monitor_test_name_python">
<a href="#connection_monitor_test_name_python" style="color: inherit; text-decoration: inherit;">connection_<wbr>monitor_<wbr>test_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the connection monitor test{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="peering_service_name_python">
<a href="#peering_service_name_python" style="color: inherit; text-decoration: inherit;">peering_<wbr>service_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the peering service.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resource_group_name_python">
<a href="#resource_group_name_python" style="color: inherit; text-decoration: inherit;">resource_<wbr>group_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the resource group.{{% /md %}}</dd></dl>
{{% /choosable %}}




## getConnectionMonitorTest Result {#result}

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
    <dd>{{% md %}}The ID of the resource.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="istestsuccessful_csharp">
<a href="#istestsuccessful_csharp" style="color: inherit; text-decoration: inherit;">Is<wbr>Test<wbr>Successful</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}The flag that indicates if the Connection Monitor test is successful or not.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the resource.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="path_csharp">
<a href="#path_csharp" style="color: inherit; text-decoration: inherit;">Path</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;string&gt;</span>
    </dt>
    <dd>{{% md %}}The path representing the Connection Monitor test.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="provisioningstate_csharp">
<a href="#provisioningstate_csharp" style="color: inherit; text-decoration: inherit;">Provisioning<wbr>State</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provisioning state of the resource.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="type_csharp">
<a href="#type_csharp" style="color: inherit; text-decoration: inherit;">Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the resource.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="destination_csharp">
<a href="#destination_csharp" style="color: inherit; text-decoration: inherit;">Destination</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Connection Monitor test destination{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="destinationport_csharp">
<a href="#destinationport_csharp" style="color: inherit; text-decoration: inherit;">Destination<wbr>Port</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The Connection Monitor test destination port{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="sourceagent_csharp">
<a href="#sourceagent_csharp" style="color: inherit; text-decoration: inherit;">Source<wbr>Agent</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Connection Monitor test source agent{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="testfrequencyinsec_csharp">
<a href="#testfrequencyinsec_csharp" style="color: inherit; text-decoration: inherit;">Test<wbr>Frequency<wbr>In<wbr>Sec</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The Connection Monitor test frequency in seconds{{% /md %}}</dd></dl>
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
    <dd>{{% md %}}The ID of the resource.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="istestsuccessful_go">
<a href="#istestsuccessful_go" style="color: inherit; text-decoration: inherit;">Is<wbr>Test<wbr>Successful</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}The flag that indicates if the Connection Monitor test is successful or not.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_go">
<a href="#name_go" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the resource.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="path_go">
<a href="#path_go" style="color: inherit; text-decoration: inherit;">Path</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The path representing the Connection Monitor test.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="provisioningstate_go">
<a href="#provisioningstate_go" style="color: inherit; text-decoration: inherit;">Provisioning<wbr>State</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provisioning state of the resource.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="type_go">
<a href="#type_go" style="color: inherit; text-decoration: inherit;">Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the resource.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="destination_go">
<a href="#destination_go" style="color: inherit; text-decoration: inherit;">Destination</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Connection Monitor test destination{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="destinationport_go">
<a href="#destinationport_go" style="color: inherit; text-decoration: inherit;">Destination<wbr>Port</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The Connection Monitor test destination port{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="sourceagent_go">
<a href="#sourceagent_go" style="color: inherit; text-decoration: inherit;">Source<wbr>Agent</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Connection Monitor test source agent{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="testfrequencyinsec_go">
<a href="#testfrequencyinsec_go" style="color: inherit; text-decoration: inherit;">Test<wbr>Frequency<wbr>In<wbr>Sec</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The Connection Monitor test frequency in seconds{{% /md %}}</dd></dl>
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
    <dd>{{% md %}}The ID of the resource.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="istestsuccessful_nodejs">
<a href="#istestsuccessful_nodejs" style="color: inherit; text-decoration: inherit;">is<wbr>Test<wbr>Successful</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}The flag that indicates if the Connection Monitor test is successful or not.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_nodejs">
<a href="#name_nodejs" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the resource.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="path_nodejs">
<a href="#path_nodejs" style="color: inherit; text-decoration: inherit;">path</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The path representing the Connection Monitor test.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="provisioningstate_nodejs">
<a href="#provisioningstate_nodejs" style="color: inherit; text-decoration: inherit;">provisioning<wbr>State</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provisioning state of the resource.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="type_nodejs">
<a href="#type_nodejs" style="color: inherit; text-decoration: inherit;">type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the resource.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="destination_nodejs">
<a href="#destination_nodejs" style="color: inherit; text-decoration: inherit;">destination</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Connection Monitor test destination{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="destinationport_nodejs">
<a href="#destinationport_nodejs" style="color: inherit; text-decoration: inherit;">destination<wbr>Port</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The Connection Monitor test destination port{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="sourceagent_nodejs">
<a href="#sourceagent_nodejs" style="color: inherit; text-decoration: inherit;">source<wbr>Agent</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Connection Monitor test source agent{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="testfrequencyinsec_nodejs">
<a href="#testfrequencyinsec_nodejs" style="color: inherit; text-decoration: inherit;">test<wbr>Frequency<wbr>In<wbr>Sec</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The Connection Monitor test frequency in seconds{{% /md %}}</dd></dl>
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
    <dd>{{% md %}}The ID of the resource.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="is_test_successful_python">
<a href="#is_test_successful_python" style="color: inherit; text-decoration: inherit;">is_<wbr>test_<wbr>successful</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}The flag that indicates if the Connection Monitor test is successful or not.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_python">
<a href="#name_python" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the resource.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="path_python">
<a href="#path_python" style="color: inherit; text-decoration: inherit;">path</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[str]</span>
    </dt>
    <dd>{{% md %}}The path representing the Connection Monitor test.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="provisioning_state_python">
<a href="#provisioning_state_python" style="color: inherit; text-decoration: inherit;">provisioning_<wbr>state</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The provisioning state of the resource.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="type_python">
<a href="#type_python" style="color: inherit; text-decoration: inherit;">type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of the resource.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="destination_python">
<a href="#destination_python" style="color: inherit; text-decoration: inherit;">destination</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Connection Monitor test destination{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="destination_port_python">
<a href="#destination_port_python" style="color: inherit; text-decoration: inherit;">destination_<wbr>port</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The Connection Monitor test destination port{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="source_agent_python">
<a href="#source_agent_python" style="color: inherit; text-decoration: inherit;">source_<wbr>agent</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Connection Monitor test source agent{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="test_frequency_in_sec_python">
<a href="#test_frequency_in_sec_python" style="color: inherit; text-decoration: inherit;">test_<wbr>frequency_<wbr>in_<wbr>sec</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The Connection Monitor test frequency in seconds{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-azure-native">https://github.com/pulumi/pulumi-azure-native</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
</dl>
