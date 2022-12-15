# Build Harness Bootstrap

This repo contains a thin makefile that simply pulls our fork of [build-harness](https://github.com/stolostron/build-harness) and our [build-harness-extensions](https://github.com/stolostron/build-harness-extensions) using the method documented in the [build-harness-extensions readme](https://github.com/stolostron/build-harness-extensions#extensions-to-build-harness).  

## Use

Invoke `make` in the root directory of this project to pull the build harness and build harness extensions.  From there, you'll be able to access the build harness fully!

## Errors

In the case of issues using the v4 API certain users may find deleting `.build-harness.bootstrap` and using the v3 API command

```-include $(shell [ -f ".build-harness-bootstrap" ] || curl -sL -o .build-harness-bootstrap -H "Authorization: token $(GITHUB_TOKEN)" -H "Accept: application/vnd.github.v3.raw" "https://raw.github.com/stolostron/build-harness-extensions/main/templates/Makefile.build-harness-bootstrap"; echo .build-harness-bootstrap)```

to have better results
