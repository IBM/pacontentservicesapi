---
title: API Reference



toc_footers:
  - <a href='https://www.ibm.com/support/knowledgecenter/SSD29G_2.0.0/main/welcome.html'>Full Planning Analytics documentation</a>

includes:
  - requests
  - post
  - get
  - del
  - put

search: true
---

# Introduction

The IBM Planning Analytics Content Services API can be used to create, retrieve, delete, or update assets in IBM Planning Analytics Workspace.

# Headers 

To use the Planning Analytics Content Services API, include the following headers in your requests.

## Content-Type

Use `application/json` when making requests to the Planning Analytics Content Services API.

## ba-sso-authenticity

The `ba-sso-authenticity` is the Business Analytics single sign-on authentication value. The value can be found in your cookies, under the name `ba-sso-csrf`.

## cookie

> Example of the redirect javascript:

```
<html>
    <head>
        <script>
            document.location.replace | GET THIS EXAMPLE FROM JACKSON
        </script>
    </head>
</html>
```

The `cookie` is the client-side cookie for Planning Analytics Workspace. Cookies must be defined, otherwise your request will not be authenticated. You can use a javascript file to redirect you to the login page. After you log in, your cookies will be set in the browser. 

The value can be found in your cookies, by combining `wa-current-userid`, `ba-sso-csrf` and `paSession`.

For example:

`wa-current-userid=N9UFBGNPY8HO; ba-sso-csrf=Y7YjUGVYot+5eZZW9KFyqnMXa0s=; paSession=s%3A2wglGfmeBaX4CIawGqRSO1aUTDrs4ytD.dH7HqmL8uhH%2B%2Bz4jq6zVkaxGlZ1%2FMWQVBBqHllu3wJY`