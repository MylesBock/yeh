# yeh
a poorly named helm chart wrapping https://github.com/rakyll/hey

## quickstart
(assuming your cwd is the root of this repo)
1. Build the image (`docker build -t (your-registry)/hey:(some tag) docker/`)
2. Spin up a cluster with k3d or kind (briefly tested with both)
3. Create a snippet of yaml to feed in with `helm install -f (some file).yaml` overriding `HEY_TARGET`
3. `helm install -n (desired namespace) yeh chart/`

Most flags are represented as environment variables in `chart/values.yaml`, please understand
yes that is case sensitive (this chart is hacky and that was generated with some janky tooling I wrote a few weeks ago)
