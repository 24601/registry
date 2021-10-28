
---
title: "getAccessCredentials"
title_tag: "vault.azure.getAccessCredentials"
meta_desc: "Documentation for the vault.azure.getAccessCredentials function with examples, input properties, output properties, and supporting types."
layout: api
no_edit_this_page: true
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->




## Using getAccessCredentials {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getAccessCredentials<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetAccessCredentialsArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetAccessCredentialsResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_access_credentials(</span><span class="nx">backend</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                           <span class="nx">max_cred_validation_seconds</span><span class="p">:</span> <span class="nx">Optional[int]</span> = None<span class="p">,</span>
                           <span class="nx">num_seconds_between_tests</span><span class="p">:</span> <span class="nx">Optional[int]</span> = None<span class="p">,</span>
                           <span class="nx">num_sequential_successes</span><span class="p">:</span> <span class="nx">Optional[int]</span> = None<span class="p">,</span>
                           <span class="nx">role</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                           <span class="nx">validate_creds</span><span class="p">:</span> <span class="nx">Optional[bool]</span> = None<span class="p">,</span>
                           <span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetAccessCredentialsResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetAccessCredentials<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">,</span> <span class="nx">args</span><span class="p"> *</span><span class="nx">GetAccessCredentialsArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">GetAccessCredentialsResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `GetAccessCredentials` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetAccessCredentials </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetAccessCredentialsResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetAccessCredentialsArgs</span><span class="p"> </span><span class="nx">args<span class="p">,</span> <span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="backend_csharp">
<a href="#backend_csharp" style="color: inherit; text-decoration: inherit;">Backend</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The path to the Azure secret backend to
read credentials from, with no leading or trailing `/`s.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="role_csharp">
<a href="#role_csharp" style="color: inherit; text-decoration: inherit;">Role</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the Azure secret backend role to read
credentials from, with no leading or trailing `/`s.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="maxcredvalidationseconds_csharp">
<a href="#maxcredvalidationseconds_csharp" style="color: inherit; text-decoration: inherit;">Max<wbr>Cred<wbr>Validation<wbr>Seconds</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}If 'validate_creds' is true, 
the number of seconds after which to give up validating credentials. Defaults
to 1,200 (20 minutes).
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="numsecondsbetweentests_csharp">
<a href="#numsecondsbetweentests_csharp" style="color: inherit; text-decoration: inherit;">Num<wbr>Seconds<wbr>Between<wbr>Tests</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}If 'validate_creds' is true, 
the number of seconds to wait between each test of generated credentials.
Defaults to 7.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="numsequentialsuccesses_csharp">
<a href="#numsequentialsuccesses_csharp" style="color: inherit; text-decoration: inherit;">Num<wbr>Sequential<wbr>Successes</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}If 'validate_creds' is true, 
the number of sequential successes required to validate generated
credentials. Defaults to 8.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="validatecreds_csharp">
<a href="#validatecreds_csharp" style="color: inherit; text-decoration: inherit;">Validate<wbr>Creds</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether generated credentials should be 
validated before being returned. Defaults to `false`, which returns
credentials without checking whether they have fully propagated throughout
Azure Active Directory. Designating `true` activates testing.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="backend_go">
<a href="#backend_go" style="color: inherit; text-decoration: inherit;">Backend</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The path to the Azure secret backend to
read credentials from, with no leading or trailing `/`s.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="role_go">
<a href="#role_go" style="color: inherit; text-decoration: inherit;">Role</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the Azure secret backend role to read
credentials from, with no leading or trailing `/`s.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="maxcredvalidationseconds_go">
<a href="#maxcredvalidationseconds_go" style="color: inherit; text-decoration: inherit;">Max<wbr>Cred<wbr>Validation<wbr>Seconds</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}If 'validate_creds' is true, 
the number of seconds after which to give up validating credentials. Defaults
to 1,200 (20 minutes).
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="numsecondsbetweentests_go">
<a href="#numsecondsbetweentests_go" style="color: inherit; text-decoration: inherit;">Num<wbr>Seconds<wbr>Between<wbr>Tests</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}If 'validate_creds' is true, 
the number of seconds to wait between each test of generated credentials.
Defaults to 7.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="numsequentialsuccesses_go">
<a href="#numsequentialsuccesses_go" style="color: inherit; text-decoration: inherit;">Num<wbr>Sequential<wbr>Successes</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}If 'validate_creds' is true, 
the number of sequential successes required to validate generated
credentials. Defaults to 8.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="validatecreds_go">
<a href="#validatecreds_go" style="color: inherit; text-decoration: inherit;">Validate<wbr>Creds</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether generated credentials should be 
validated before being returned. Defaults to `false`, which returns
credentials without checking whether they have fully propagated throughout
Azure Active Directory. Designating `true` activates testing.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="backend_nodejs">
<a href="#backend_nodejs" style="color: inherit; text-decoration: inherit;">backend</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The path to the Azure secret backend to
read credentials from, with no leading or trailing `/`s.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="role_nodejs">
<a href="#role_nodejs" style="color: inherit; text-decoration: inherit;">role</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the Azure secret backend role to read
credentials from, with no leading or trailing `/`s.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="maxcredvalidationseconds_nodejs">
<a href="#maxcredvalidationseconds_nodejs" style="color: inherit; text-decoration: inherit;">max<wbr>Cred<wbr>Validation<wbr>Seconds</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}If 'validate_creds' is true, 
the number of seconds after which to give up validating credentials. Defaults
to 1,200 (20 minutes).
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="numsecondsbetweentests_nodejs">
<a href="#numsecondsbetweentests_nodejs" style="color: inherit; text-decoration: inherit;">num<wbr>Seconds<wbr>Between<wbr>Tests</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}If 'validate_creds' is true, 
the number of seconds to wait between each test of generated credentials.
Defaults to 7.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="numsequentialsuccesses_nodejs">
<a href="#numsequentialsuccesses_nodejs" style="color: inherit; text-decoration: inherit;">num<wbr>Sequential<wbr>Successes</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}If 'validate_creds' is true, 
the number of sequential successes required to validate generated
credentials. Defaults to 8.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="validatecreds_nodejs">
<a href="#validatecreds_nodejs" style="color: inherit; text-decoration: inherit;">validate<wbr>Creds</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Whether generated credentials should be 
validated before being returned. Defaults to `false`, which returns
credentials without checking whether they have fully propagated throughout
Azure Active Directory. Designating `true` activates testing.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="backend_python">
<a href="#backend_python" style="color: inherit; text-decoration: inherit;">backend</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The path to the Azure secret backend to
read credentials from, with no leading or trailing `/`s.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="role_python">
<a href="#role_python" style="color: inherit; text-decoration: inherit;">role</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the Azure secret backend role to read
credentials from, with no leading or trailing `/`s.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="max_cred_validation_seconds_python">
<a href="#max_cred_validation_seconds_python" style="color: inherit; text-decoration: inherit;">max_<wbr>cred_<wbr>validation_<wbr>seconds</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}If 'validate_creds' is true, 
the number of seconds after which to give up validating credentials. Defaults
to 1,200 (20 minutes).
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="num_seconds_between_tests_python">
<a href="#num_seconds_between_tests_python" style="color: inherit; text-decoration: inherit;">num_<wbr>seconds_<wbr>between_<wbr>tests</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}If 'validate_creds' is true, 
the number of seconds to wait between each test of generated credentials.
Defaults to 7.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="num_sequential_successes_python">
<a href="#num_sequential_successes_python" style="color: inherit; text-decoration: inherit;">num_<wbr>sequential_<wbr>successes</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}If 'validate_creds' is true, 
the number of sequential successes required to validate generated
credentials. Defaults to 8.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="validate_creds_python">
<a href="#validate_creds_python" style="color: inherit; text-decoration: inherit;">validate_<wbr>creds</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether generated credentials should be 
validated before being returned. Defaults to `false`, which returns
credentials without checking whether they have fully propagated throughout
Azure Active Directory. Designating `true` activates testing.
{{% /md %}}</dd></dl>
{{% /choosable %}}




## getAccessCredentials Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="backend_csharp">
<a href="#backend_csharp" style="color: inherit; text-decoration: inherit;">Backend</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="clientid_csharp">
<a href="#clientid_csharp" style="color: inherit; text-decoration: inherit;">Client<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The client id for credentials to query the Azure APIs.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="clientsecret_csharp">
<a href="#clientsecret_csharp" style="color: inherit; text-decoration: inherit;">Client<wbr>Secret</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The client secret for credentials to query the Azure APIs.
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
        <span id="leaseduration_csharp">
<a href="#leaseduration_csharp" style="color: inherit; text-decoration: inherit;">Lease<wbr>Duration</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The duration of the secret lease, in seconds relative
to the time the data was requested. Once this time has passed any plan
generated with this data may fail to apply.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="leaseid_csharp">
<a href="#leaseid_csharp" style="color: inherit; text-decoration: inherit;">Lease<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The lease identifier assigned by Vault.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="leaserenewable_csharp">
<a href="#leaserenewable_csharp" style="color: inherit; text-decoration: inherit;">Lease<wbr>Renewable</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="leasestarttime_csharp">
<a href="#leasestarttime_csharp" style="color: inherit; text-decoration: inherit;">Lease<wbr>Start<wbr>Time</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="role_csharp">
<a href="#role_csharp" style="color: inherit; text-decoration: inherit;">Role</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="maxcredvalidationseconds_csharp">
<a href="#maxcredvalidationseconds_csharp" style="color: inherit; text-decoration: inherit;">Max<wbr>Cred<wbr>Validation<wbr>Seconds</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="numsecondsbetweentests_csharp">
<a href="#numsecondsbetweentests_csharp" style="color: inherit; text-decoration: inherit;">Num<wbr>Seconds<wbr>Between<wbr>Tests</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="numsequentialsuccesses_csharp">
<a href="#numsequentialsuccesses_csharp" style="color: inherit; text-decoration: inherit;">Num<wbr>Sequential<wbr>Successes</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="validatecreds_csharp">
<a href="#validatecreds_csharp" style="color: inherit; text-decoration: inherit;">Validate<wbr>Creds</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="backend_go">
<a href="#backend_go" style="color: inherit; text-decoration: inherit;">Backend</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="clientid_go">
<a href="#clientid_go" style="color: inherit; text-decoration: inherit;">Client<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The client id for credentials to query the Azure APIs.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="clientsecret_go">
<a href="#clientsecret_go" style="color: inherit; text-decoration: inherit;">Client<wbr>Secret</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The client secret for credentials to query the Azure APIs.
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
        <span id="leaseduration_go">
<a href="#leaseduration_go" style="color: inherit; text-decoration: inherit;">Lease<wbr>Duration</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The duration of the secret lease, in seconds relative
to the time the data was requested. Once this time has passed any plan
generated with this data may fail to apply.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="leaseid_go">
<a href="#leaseid_go" style="color: inherit; text-decoration: inherit;">Lease<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The lease identifier assigned by Vault.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="leaserenewable_go">
<a href="#leaserenewable_go" style="color: inherit; text-decoration: inherit;">Lease<wbr>Renewable</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="leasestarttime_go">
<a href="#leasestarttime_go" style="color: inherit; text-decoration: inherit;">Lease<wbr>Start<wbr>Time</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="role_go">
<a href="#role_go" style="color: inherit; text-decoration: inherit;">Role</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="maxcredvalidationseconds_go">
<a href="#maxcredvalidationseconds_go" style="color: inherit; text-decoration: inherit;">Max<wbr>Cred<wbr>Validation<wbr>Seconds</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="numsecondsbetweentests_go">
<a href="#numsecondsbetweentests_go" style="color: inherit; text-decoration: inherit;">Num<wbr>Seconds<wbr>Between<wbr>Tests</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="numsequentialsuccesses_go">
<a href="#numsequentialsuccesses_go" style="color: inherit; text-decoration: inherit;">Num<wbr>Sequential<wbr>Successes</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="validatecreds_go">
<a href="#validatecreds_go" style="color: inherit; text-decoration: inherit;">Validate<wbr>Creds</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="backend_nodejs">
<a href="#backend_nodejs" style="color: inherit; text-decoration: inherit;">backend</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="clientid_nodejs">
<a href="#clientid_nodejs" style="color: inherit; text-decoration: inherit;">client<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The client id for credentials to query the Azure APIs.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="clientsecret_nodejs">
<a href="#clientsecret_nodejs" style="color: inherit; text-decoration: inherit;">client<wbr>Secret</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The client secret for credentials to query the Azure APIs.
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
        <span id="leaseduration_nodejs">
<a href="#leaseduration_nodejs" style="color: inherit; text-decoration: inherit;">lease<wbr>Duration</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The duration of the secret lease, in seconds relative
to the time the data was requested. Once this time has passed any plan
generated with this data may fail to apply.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="leaseid_nodejs">
<a href="#leaseid_nodejs" style="color: inherit; text-decoration: inherit;">lease<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The lease identifier assigned by Vault.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="leaserenewable_nodejs">
<a href="#leaserenewable_nodejs" style="color: inherit; text-decoration: inherit;">lease<wbr>Renewable</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="leasestarttime_nodejs">
<a href="#leasestarttime_nodejs" style="color: inherit; text-decoration: inherit;">lease<wbr>Start<wbr>Time</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="role_nodejs">
<a href="#role_nodejs" style="color: inherit; text-decoration: inherit;">role</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="maxcredvalidationseconds_nodejs">
<a href="#maxcredvalidationseconds_nodejs" style="color: inherit; text-decoration: inherit;">max<wbr>Cred<wbr>Validation<wbr>Seconds</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="numsecondsbetweentests_nodejs">
<a href="#numsecondsbetweentests_nodejs" style="color: inherit; text-decoration: inherit;">num<wbr>Seconds<wbr>Between<wbr>Tests</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="numsequentialsuccesses_nodejs">
<a href="#numsequentialsuccesses_nodejs" style="color: inherit; text-decoration: inherit;">num<wbr>Sequential<wbr>Successes</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="validatecreds_nodejs">
<a href="#validatecreds_nodejs" style="color: inherit; text-decoration: inherit;">validate<wbr>Creds</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="backend_python">
<a href="#backend_python" style="color: inherit; text-decoration: inherit;">backend</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="client_id_python">
<a href="#client_id_python" style="color: inherit; text-decoration: inherit;">client_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The client id for credentials to query the Azure APIs.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="client_secret_python">
<a href="#client_secret_python" style="color: inherit; text-decoration: inherit;">client_<wbr>secret</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The client secret for credentials to query the Azure APIs.
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
        <span id="lease_duration_python">
<a href="#lease_duration_python" style="color: inherit; text-decoration: inherit;">lease_<wbr>duration</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The duration of the secret lease, in seconds relative
to the time the data was requested. Once this time has passed any plan
generated with this data may fail to apply.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="lease_id_python">
<a href="#lease_id_python" style="color: inherit; text-decoration: inherit;">lease_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The lease identifier assigned by Vault.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="lease_renewable_python">
<a href="#lease_renewable_python" style="color: inherit; text-decoration: inherit;">lease_<wbr>renewable</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="lease_start_time_python">
<a href="#lease_start_time_python" style="color: inherit; text-decoration: inherit;">lease_<wbr>start_<wbr>time</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="role_python">
<a href="#role_python" style="color: inherit; text-decoration: inherit;">role</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="max_cred_validation_seconds_python">
<a href="#max_cred_validation_seconds_python" style="color: inherit; text-decoration: inherit;">max_<wbr>cred_<wbr>validation_<wbr>seconds</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="num_seconds_between_tests_python">
<a href="#num_seconds_between_tests_python" style="color: inherit; text-decoration: inherit;">num_<wbr>seconds_<wbr>between_<wbr>tests</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="num_sequential_successes_python">
<a href="#num_sequential_successes_python" style="color: inherit; text-decoration: inherit;">num_<wbr>sequential_<wbr>successes</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="validate_creds_python">
<a href="#validate_creds_python" style="color: inherit; text-decoration: inherit;">validate_<wbr>creds</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-vault">https://github.com/pulumi/pulumi-vault</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`vault` Terraform Provider](https://github.com/hashicorp/terraform-provider-vault).{{% /md %}}</dd>
</dl>
