---
lang: en
title: 'Reserved binding keys'
keywords: LoopBack 4.0, LoopBack 4
toc_level: 1
sidebar: lb4_sidebar
permalink: /doc/en/lb4/Reserved-binding-keys.html
---

## Overview

When using [dependency injection](Dependency-injection.md) there are a few
things to keep in mind with regards to binding keys.

Different packages and components for LoopBack 4 may have some bindings already
defined. You can change the default behavior by overriding the default binding,
but you must ensure the interface of the new binding is the same as the default
(but behavior can be different).

It is recommended to use the CONSTANT defined for each binding key in it's
respective namespace. You can import a namespace and access the binding key in
your application as follows:

```js
import {BindingKeyNameSpace} from 'package-name';

app.bind(BindKeyNameSpace.KeyName).to('value');
```

Following is a list of links to the apidocs on the binding keys in use by
various `@loopback` packages:

{% include note.html title="Declaring new binding keys" content="
For component developers creating a new Binding, to avoid conflict with other
packages, it is recommended that the binding key start with the package name as
the prefix. Example: `@loopback/authentication` component uses the prefix
`authentication` for its binding keys.
" %}

- [AuthenticationBindings](http://apidocs.loopback.io/@loopback%2fdocs/authentication.html#AuthenticationBindings)
- [BootBindings](http://apidocs.loopback.io/@loopback%2fdocs/boot.html#BootBindings)
- [CoreBindings](http://apidocs.loopback.io/@loopback%2fdocs/core.html#CoreBindings)
- [RestBindings](http://apidocs.loopback.io/@loopback%2fdocs/rest.html#RestBindings)
- [RestBindings.Http](http://apidocs.loopback.io/@loopback%2fdocs/rest.html#Http)
- [RestBindings.SequenceActions](http://apidocs.loopback.io/@loopback%2fdocs/rest.html#SequenceActions)
