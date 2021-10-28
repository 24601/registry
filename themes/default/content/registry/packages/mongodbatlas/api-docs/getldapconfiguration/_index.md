
---
title: "getLdapConfiguration"
title_tag: "mongodbatlas.getLdapConfiguration"
meta_desc: "Documentation for the mongodbatlas.getLdapConfiguration function with examples, input properties, output properties, and supporting types."
layout: api
no_edit_this_page: true
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

`mongodbatlas.LdapConfiguration` describes a LDAP Configuration.

> **NOTE:** Groups and projects are synonymous terms. You may find **group_id** in the official documentation.




## Using getLdapConfiguration {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getLdapConfiguration<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetLdapConfigurationArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetLdapConfigurationResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_ldap_configuration(</span><span class="nx">project_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">,</span>
                           <span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetLdapConfigurationResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupLdapConfiguration<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">,</span> <span class="nx">args</span><span class="p"> *</span><span class="nx">LookupLdapConfigurationArgs</span><span class="p">,</span> <span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">LookupLdapConfigurationResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `LookupLdapConfiguration` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetLdapConfiguration </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetLdapConfigurationResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetLdapConfigurationArgs</span><span class="p"> </span><span class="nx">args<span class="p">,</span> <span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="projectid_csharp">
<a href="#projectid_csharp" style="color: inherit; text-decoration: inherit;">Project<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier for the Atlas project associated with the LDAP over TLS/SSL configuration.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="projectid_go">
<a href="#projectid_go" style="color: inherit; text-decoration: inherit;">Project<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier for the Atlas project associated with the LDAP over TLS/SSL configuration.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="projectid_nodejs">
<a href="#projectid_nodejs" style="color: inherit; text-decoration: inherit;">project<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier for the Atlas project associated with the LDAP over TLS/SSL configuration.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="project_id_python">
<a href="#project_id_python" style="color: inherit; text-decoration: inherit;">project_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier for the Atlas project associated with the LDAP over TLS/SSL configuration.
{{% /md %}}</dd></dl>
{{% /choosable %}}




## getLdapConfiguration Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="authenticationenabled_csharp">
<a href="#authenticationenabled_csharp" style="color: inherit; text-decoration: inherit;">Authentication<wbr>Enabled</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether user authentication with LDAP is enabled.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="authorizationenabled_csharp">
<a href="#authorizationenabled_csharp" style="color: inherit; text-decoration: inherit;">Authorization<wbr>Enabled</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether user authorization with LDAP is enabled.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="authzquerytemplate_csharp">
<a href="#authzquerytemplate_csharp" style="color: inherit; text-decoration: inherit;">Authz<wbr>Query<wbr>Template</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}An LDAP query template that Atlas executes to obtain the LDAP groups to which the authenticated user belongs.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="bindpassword_csharp">
<a href="#bindpassword_csharp" style="color: inherit; text-decoration: inherit;">Bind<wbr>Password</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The password used to authenticate the `bind_username`.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="bindusername_csharp">
<a href="#bindusername_csharp" style="color: inherit; text-decoration: inherit;">Bind<wbr>Username</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The user DN that Atlas uses to connect to the LDAP server.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="cacertificate_csharp">
<a href="#cacertificate_csharp" style="color: inherit; text-decoration: inherit;">Ca<wbr>Certificate</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}CA certificate used to verify the identify of the LDAP server.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="hostname_csharp">
<a href="#hostname_csharp" style="color: inherit; text-decoration: inherit;">Hostname</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}(Required) The hostname or IP address of the LDAP server.
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
        <span id="port_csharp">
<a href="#port_csharp" style="color: inherit; text-decoration: inherit;">Port</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The port to which the LDAP server listens for client connections.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="projectid_csharp">
<a href="#projectid_csharp" style="color: inherit; text-decoration: inherit;">Project<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="usertodnmappings_csharp">
<a href="#usertodnmappings_csharp" style="color: inherit; text-decoration: inherit;">User<wbr>To<wbr>Dn<wbr>Mappings</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getldapconfigurationusertodnmapping">List&lt;Get<wbr>Ldap<wbr>Configuration<wbr>User<wbr>To<wbr>Dn<wbr>Mapping&gt;</a></span>
    </dt>
    <dd>{{% md %}}Maps an LDAP username for authentication to an LDAP Distinguished Name (DN).
* `user_to_dn_mapping.0.match` - A regular expression to match against a provided LDAP username.
* `user_to_dn_mapping.0.substitution` - An LDAP Distinguished Name (DN) formatting template that converts the LDAP name matched by the `match` regular expression into an LDAP Distinguished Name.
* `user_to_dn_mapping.0.ldap_query` - An LDAP query formatting template that inserts the LDAP name matched by the `match` regular expression into an LDAP query URI as specified by RFC 4515 and RFC 4516.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="authenticationenabled_go">
<a href="#authenticationenabled_go" style="color: inherit; text-decoration: inherit;">Authentication<wbr>Enabled</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether user authentication with LDAP is enabled.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="authorizationenabled_go">
<a href="#authorizationenabled_go" style="color: inherit; text-decoration: inherit;">Authorization<wbr>Enabled</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether user authorization with LDAP is enabled.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="authzquerytemplate_go">
<a href="#authzquerytemplate_go" style="color: inherit; text-decoration: inherit;">Authz<wbr>Query<wbr>Template</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}An LDAP query template that Atlas executes to obtain the LDAP groups to which the authenticated user belongs.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="bindpassword_go">
<a href="#bindpassword_go" style="color: inherit; text-decoration: inherit;">Bind<wbr>Password</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The password used to authenticate the `bind_username`.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="bindusername_go">
<a href="#bindusername_go" style="color: inherit; text-decoration: inherit;">Bind<wbr>Username</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The user DN that Atlas uses to connect to the LDAP server.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="cacertificate_go">
<a href="#cacertificate_go" style="color: inherit; text-decoration: inherit;">Ca<wbr>Certificate</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}CA certificate used to verify the identify of the LDAP server.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="hostname_go">
<a href="#hostname_go" style="color: inherit; text-decoration: inherit;">Hostname</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}(Required) The hostname or IP address of the LDAP server.
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
        <span id="port_go">
<a href="#port_go" style="color: inherit; text-decoration: inherit;">Port</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The port to which the LDAP server listens for client connections.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="projectid_go">
<a href="#projectid_go" style="color: inherit; text-decoration: inherit;">Project<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="usertodnmappings_go">
<a href="#usertodnmappings_go" style="color: inherit; text-decoration: inherit;">User<wbr>To<wbr>Dn<wbr>Mappings</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getldapconfigurationusertodnmapping">[]Get<wbr>Ldap<wbr>Configuration<wbr>User<wbr>To<wbr>Dn<wbr>Mapping</a></span>
    </dt>
    <dd>{{% md %}}Maps an LDAP username for authentication to an LDAP Distinguished Name (DN).
* `user_to_dn_mapping.0.match` - A regular expression to match against a provided LDAP username.
* `user_to_dn_mapping.0.substitution` - An LDAP Distinguished Name (DN) formatting template that converts the LDAP name matched by the `match` regular expression into an LDAP Distinguished Name.
* `user_to_dn_mapping.0.ldap_query` - An LDAP query formatting template that inserts the LDAP name matched by the `match` regular expression into an LDAP query URI as specified by RFC 4515 and RFC 4516.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="authenticationenabled_nodejs">
<a href="#authenticationenabled_nodejs" style="color: inherit; text-decoration: inherit;">authentication<wbr>Enabled</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Specifies whether user authentication with LDAP is enabled.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="authorizationenabled_nodejs">
<a href="#authorizationenabled_nodejs" style="color: inherit; text-decoration: inherit;">authorization<wbr>Enabled</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Specifies whether user authorization with LDAP is enabled.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="authzquerytemplate_nodejs">
<a href="#authzquerytemplate_nodejs" style="color: inherit; text-decoration: inherit;">authz<wbr>Query<wbr>Template</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}An LDAP query template that Atlas executes to obtain the LDAP groups to which the authenticated user belongs.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="bindpassword_nodejs">
<a href="#bindpassword_nodejs" style="color: inherit; text-decoration: inherit;">bind<wbr>Password</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The password used to authenticate the `bind_username`.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="bindusername_nodejs">
<a href="#bindusername_nodejs" style="color: inherit; text-decoration: inherit;">bind<wbr>Username</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The user DN that Atlas uses to connect to the LDAP server.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="cacertificate_nodejs">
<a href="#cacertificate_nodejs" style="color: inherit; text-decoration: inherit;">ca<wbr>Certificate</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}CA certificate used to verify the identify of the LDAP server.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="hostname_nodejs">
<a href="#hostname_nodejs" style="color: inherit; text-decoration: inherit;">hostname</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}(Required) The hostname or IP address of the LDAP server.
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
        <span id="port_nodejs">
<a href="#port_nodejs" style="color: inherit; text-decoration: inherit;">port</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The port to which the LDAP server listens for client connections.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="projectid_nodejs">
<a href="#projectid_nodejs" style="color: inherit; text-decoration: inherit;">project<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="usertodnmappings_nodejs">
<a href="#usertodnmappings_nodejs" style="color: inherit; text-decoration: inherit;">user<wbr>To<wbr>Dn<wbr>Mappings</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getldapconfigurationusertodnmapping">Get<wbr>Ldap<wbr>Configuration<wbr>User<wbr>To<wbr>Dn<wbr>Mapping[]</a></span>
    </dt>
    <dd>{{% md %}}Maps an LDAP username for authentication to an LDAP Distinguished Name (DN).
* `user_to_dn_mapping.0.match` - A regular expression to match against a provided LDAP username.
* `user_to_dn_mapping.0.substitution` - An LDAP Distinguished Name (DN) formatting template that converts the LDAP name matched by the `match` regular expression into an LDAP Distinguished Name.
* `user_to_dn_mapping.0.ldap_query` - An LDAP query formatting template that inserts the LDAP name matched by the `match` regular expression into an LDAP query URI as specified by RFC 4515 and RFC 4516.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="authentication_enabled_python">
<a href="#authentication_enabled_python" style="color: inherit; text-decoration: inherit;">authentication_<wbr>enabled</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether user authentication with LDAP is enabled.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="authorization_enabled_python">
<a href="#authorization_enabled_python" style="color: inherit; text-decoration: inherit;">authorization_<wbr>enabled</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether user authorization with LDAP is enabled.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="authz_query_template_python">
<a href="#authz_query_template_python" style="color: inherit; text-decoration: inherit;">authz_<wbr>query_<wbr>template</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}An LDAP query template that Atlas executes to obtain the LDAP groups to which the authenticated user belongs.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="bind_password_python">
<a href="#bind_password_python" style="color: inherit; text-decoration: inherit;">bind_<wbr>password</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The password used to authenticate the `bind_username`.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="bind_username_python">
<a href="#bind_username_python" style="color: inherit; text-decoration: inherit;">bind_<wbr>username</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The user DN that Atlas uses to connect to the LDAP server.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="ca_certificate_python">
<a href="#ca_certificate_python" style="color: inherit; text-decoration: inherit;">ca_<wbr>certificate</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}CA certificate used to verify the identify of the LDAP server.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="hostname_python">
<a href="#hostname_python" style="color: inherit; text-decoration: inherit;">hostname</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}(Required) The hostname or IP address of the LDAP server.
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
        <span id="port_python">
<a href="#port_python" style="color: inherit; text-decoration: inherit;">port</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The port to which the LDAP server listens for client connections.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="project_id_python">
<a href="#project_id_python" style="color: inherit; text-decoration: inherit;">project_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="user_to_dn_mappings_python">
<a href="#user_to_dn_mappings_python" style="color: inherit; text-decoration: inherit;">user_<wbr>to_<wbr>dn_<wbr>mappings</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getldapconfigurationusertodnmapping">Sequence[Get<wbr>Ldap<wbr>Configuration<wbr>User<wbr>To<wbr>Dn<wbr>Mapping]</a></span>
    </dt>
    <dd>{{% md %}}Maps an LDAP username for authentication to an LDAP Distinguished Name (DN).
* `user_to_dn_mapping.0.match` - A regular expression to match against a provided LDAP username.
* `user_to_dn_mapping.0.substitution` - An LDAP Distinguished Name (DN) formatting template that converts the LDAP name matched by the `match` regular expression into an LDAP Distinguished Name.
* `user_to_dn_mapping.0.ldap_query` - An LDAP query formatting template that inserts the LDAP name matched by the `match` regular expression into an LDAP query URI as specified by RFC 4515 and RFC 4516.
{{% /md %}}</dd></dl>
{{% /choosable %}}




## Supporting Types


<h4 id="getldapconfigurationusertodnmapping">Get<wbr>Ldap<wbr>Configuration<wbr>User<wbr>To<wbr>Dn<wbr>Mapping</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="ldapquery_csharp">
<a href="#ldapquery_csharp" style="color: inherit; text-decoration: inherit;">Ldap<wbr>Query</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="match_csharp">
<a href="#match_csharp" style="color: inherit; text-decoration: inherit;">Match</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="substitution_csharp">
<a href="#substitution_csharp" style="color: inherit; text-decoration: inherit;">Substitution</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="ldapquery_go">
<a href="#ldapquery_go" style="color: inherit; text-decoration: inherit;">Ldap<wbr>Query</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="match_go">
<a href="#match_go" style="color: inherit; text-decoration: inherit;">Match</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="substitution_go">
<a href="#substitution_go" style="color: inherit; text-decoration: inherit;">Substitution</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="ldapquery_nodejs">
<a href="#ldapquery_nodejs" style="color: inherit; text-decoration: inherit;">ldap<wbr>Query</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="match_nodejs">
<a href="#match_nodejs" style="color: inherit; text-decoration: inherit;">match</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="substitution_nodejs">
<a href="#substitution_nodejs" style="color: inherit; text-decoration: inherit;">substitution</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="ldap_query_python">
<a href="#ldap_query_python" style="color: inherit; text-decoration: inherit;">ldap_<wbr>query</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="match_python">
<a href="#match_python" style="color: inherit; text-decoration: inherit;">match</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="substitution_python">
<a href="#substitution_python" style="color: inherit; text-decoration: inherit;">substitution</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-mongodbatlas">https://github.com/pulumi/pulumi-mongodbatlas</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`mongodbatlas` Terraform Provider](https://github.com/mongodb/terraform-provider-mongodbatlas).{{% /md %}}</dd>
</dl>
