
<a name="0x3_account"></a>

# Module `0x3::account`



-  [Struct `AccountPlaceholder`](#0x3_account_AccountPlaceholder)
-  [Constants](#@Constants_0)
-  [Function `create_account`](#0x3_account_create_account)
-  [Function `create_account_internal`](#0x3_account_create_account_internal)
-  [Function `create_resource_account`](#0x3_account_create_resource_account)


<pre><code><b>use</b> <a href="">0x2::account</a>;
<b>use</b> <a href="">0x2::core_addresses</a>;
<b>use</b> <a href="">0x2::signer</a>;
<b>use</b> <a href="account_authentication.md#0x3_account_authentication">0x3::account_authentication</a>;
</code></pre>



<a name="0x3_account_AccountPlaceholder"></a>

## Struct `AccountPlaceholder`

Just using to get Account module signer


<pre><code><b>struct</b> <a href="account.md#0x3_account_AccountPlaceholder">AccountPlaceholder</a>
</code></pre>



<a name="@Constants_0"></a>

## Constants


<a name="0x3_account_ErrorAccountAlreadyExists"></a>

Account already exists


<pre><code><b>const</b> <a href="account.md#0x3_account_ErrorAccountAlreadyExists">ErrorAccountAlreadyExists</a>: u64 = 1;
</code></pre>



<a name="0x3_account_ErrorAddressReserved"></a>

Cannot create account because address is reserved


<pre><code><b>const</b> <a href="account.md#0x3_account_ErrorAddressReserved">ErrorAddressReserved</a>: u64 = 2;
</code></pre>



<a name="0x3_account_create_account"></a>

## Function `create_account`

Publishes a new <code>Account</code> resource under <code>new_address</code>. A signer representing <code>new_address</code>
is returned. This way, the caller of this function can publish additional resources under
<code>new_address</code>.


<pre><code><b>public</b>(<b>friend</b>) <b>fun</b> <a href="account.md#0x3_account_create_account">create_account</a>(new_address: <b>address</b>): <a href="">signer</a>
</code></pre>



<a name="0x3_account_create_account_internal"></a>

## Function `create_account_internal`



<pre><code><b>public</b>(<b>friend</b>) <b>fun</b> <a href="account.md#0x3_account_create_account_internal">create_account_internal</a>(new_address: <b>address</b>): <a href="">signer</a>
</code></pre>



<a name="0x3_account_create_resource_account"></a>

## Function `create_resource_account`

A resource account is used to manage resources independent of an account managed by a user.
In Rooch a resource account is created based upon the sha3 256 of the source's address and additional seed data.
A resource account can only be created once


<pre><code><b>public</b> <b>fun</b> <a href="account.md#0x3_account_create_resource_account">create_resource_account</a>(source: &<a href="">signer</a>): (<a href="">signer</a>, <a href="_SignerCapability">account::SignerCapability</a>)
</code></pre>
