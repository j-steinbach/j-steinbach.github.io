---
title: Access Control lists (ACL)
---

> As such, the ACL for a Resource may be defined in a separate Resource, and retrieving a Resource with its ACL may result in extra HTTP requests being sent.

Is it possible to define the ACL in the resouce itself? Then isn't there a race-condition? Ie. first read the content triples and ignore the 'no access' ones? And how to read the resource if the container ACL disallows access?

https://docs.inrupt.com/developer-tools/javascript/client-libraries/tutorial/manage-wac/


ACP vs. WAC (-> ACL)?

UAC -> Universal Access Control?

ACP
- ACR -> Access Control Resource
  - member policies
  - ACP policies
- container = folder

Policies

    Matcher statements that specify conditions that must be satisfied for the Policy to take effect.
    Access mode statements that specify which access modes are allowed and/or denied to the agent(s) satisfying the Matcher statements.

https://docs.inrupt.com/developer-tools/javascript/client-libraries/tutorial/manage-acp/

How to define groups?
