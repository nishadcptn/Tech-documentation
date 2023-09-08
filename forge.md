---
description: >-
  Forge is a cloud development platform created by Atlassian. It allows
  developers to create,host,and manage Cloud-based applications.
---

# Forge



**Useful Commands for creating forge apps**

```
npm install -g @forge/cli
```

```
forge login
```

```
forge create
```

<figure><img src=".gitbook/assets/image (1).png" alt=""><figcaption><p>Use Custom UI</p></figcaption></figure>

<figure><img src=".gitbook/assets/image (2).png" alt=""><figcaption><p>Use jira-global-page</p></figcaption></figure>

This will create a folder structure

<figure><img src=".gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

All the scopes and triggers are added in manifest.yml file

<figure><img src=".gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

Currently used event triggers are:

```yaml
trigger:
    - key: lifecycle-trigger
      events:
        - 'avi:forge:installed:app'
        - 'avi:jira:assigned:issue'
        - 'avi:jira:updated:issue'
webtrigger:
    - key: issue-adder
      function: issue-adder-runner
    - key: scheduled-trigger
      function: schedule-runner
```



```
forge deploy // for development purpose
forge deploy -e production // for production purpose
```

```
forge install
```

```
forge tunnel //Tunneling allows you to speed up development by avoiding the need to 
redeploy each code change, and by seeing each invocation as it executes.
```
