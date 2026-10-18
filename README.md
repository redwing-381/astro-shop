# astro-shop

The demo shop for [Why-Graph](https://github.com/redwing-381/we-make-devs-hack): nine services in the shape of the
OpenTelemetry demo's Astronomy Shop (Apache-2.0). Our AI SDE team (in Band) ships changes here as pull requests.

- `config/services.yaml` holds each service's timeouts to its dependencies, plus the simulated latency of each
  service.
- On every merge to `main`, Why-Graph's simulator (`scenarios/astro_sim.py` in the Why-Graph repo) deploys the new
  config.
- A timeout set below the callee's normal p99 latency makes the caller fail, and the simulator raises alerts for
  Why-Graph to investigate.

Change only `config/services.yaml`, always through a pull request.
