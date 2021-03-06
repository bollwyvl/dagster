---
title: pipeline_tags
description: How to use pipeline tags
---

# pipeline_tags

A Dagster pipeline can be annotated with `tags`, which contains arbitrary metadata for any
execution run of the pipeline. Tag values that are not strings will be json encoded and must meet
the criteria that `json.loads(json.dumps(value)) == value`. In this example, we have a pipeline
`my_pipeline` that contains `tags={'owner': 'ml_team'}`.

Previous Pipeline Runs are searchable by `tags`, which are stored on the Pipeline Run in the
Run Storage. To search previous Pipeline Runs in Dagit, navigate to the Runs tab and enter the
filter `tag:owner=ml_team`.

Tag values can be overwritten at pipeline invocation time. To try this in Dagit, navigate to
Playground tab and click `Edit Tags` to modify tags for that run.

As an aside, during the execution of the pipeline, `tags` can be accessed from the `context`
of the solid (as seen in `get_tag`) although it is not recommended to use tags to drive logic.

# Open in Playground

Open up this example in a playground using [Gitpod](https://gitpod.io)

[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#EXAMPLE=pipeline_tags/https://github.com/dagster-io/dagster)

# Download Manually

Download the example:

```
curl https://codeload.github.com/dagster-io/dagster/tar.gz/master | tar -xz --strip=2 dagster-master/examples/pipeline_tags
cd pipeline_tags
```
