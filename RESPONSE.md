## Part 1

> What does a Deployment give you that a bare Pod doesn't? Why do we need a separate Service object instead of talking to a Pod's IP directly?
>
> A deployment is able to manage pods. They are able to restart pods that get deleted or fail. You can also easily scale with Deployments as they can spin up new pods to handle more load. New pods get started up and shutted down all the time, so we can't really keep track of all the nodes' IP addresses. The Service provides a level of abstraction on top of the nodes so we can just use the Service's interface instead and it'll route to the pods.

## Part 2

> What is a Helm chart, and how do `values.yaml` plus `-f`/`--set` let the same chart produce different Kubernetes resources for different environments? Why is this better than keeping separate copies of your Part 1 manifests for staging and production?
>
> A Helm chart is a directory of manifest templates along with a values.yaml for the defaults. To override those, we can first use -f to specify a different yaml and then on top of that you can use --set to override an individual value from the yaml. This is better than keeping separate copies of the Part 1 manifests for staging and production because we can keep a shared version of the configuration in one set of templates.