---
title: "bom generate"
linkTitle: "bom generate"
tags: ["reference"]
date: 2022-06-27
description: bom generate → Create SPDX SBOMs

---

## bom generate

### Synopsis

bom generate → Create SPDX SBOMs

generate is the bom subcommand to generate SPDX manifests.

Currently supports creating SBOM from files, images, and docker
archives (images in tarballs). It supports pulling images from
remote registries for analysis.

bom can take a deeper look into images using a growing number
of analyzers designed to add more sense to common base images.

The SBOM data can also be exported to an in-toto provenance
attestation. The output will produce a provenance statement listing all
the SPDX data as in-toto subjects, but otherwise ready to be
completed by a later stage in your CI/CD pipeline. See the
--provenance flag for more details.



```
bom generate [flags]
```

### Options

```
  -a, --analyze-images          go deeper into images using the available analyzers
      --archive strings         list of archives to add as packages (supports tar, tar.gz)
  -c, --config string           path to yaml SBOM configuration file
  -d, --dirs strings            list of directories to include in the manifest as packages
  -f, --file strings            list of files to include
      --format string           format of the document (supports tag-value, json) (default "tag-value")
  -h, --help                    help for generate
      --ignore strings          list of regexp patterns to ignore when scanning directories
  -i, --image strings           list of images
      --image-archive strings   list of docker archive tarballs to include in the manifest
  -l, --license string          SPDX license identifier to declare in the SBOM
      --name string             name for the document, in contrast to URLs, intended for humans
  -n, --namespace string        an URI that servers as namespace for the SPDX doc
      --no-gitignore            don't use exclusions from .gitignore files
      --no-gomod                don't perform go.mod analysis, sbom will not include data about go packages
      --no-transient            don't include transient go dependencies, only direct deps from go.mod
  -o, --output string           path to the file where the document will be written (defaults to STDOUT)
      --provenance string       path to export the SBOM as an in-toto provenance statement
      --scan-images             scan container images to look for OS information (currently debian only) (default true)
```

### Options inherited from parent commands

```
      --log-level string   the logging verbosity, either 'panic', 'fatal', 'error', 'warning', 'info', 'debug', 'trace' (default "info")
```

### SEE ALSO

* [bom](bom.md)	 - A tool for working with SPDX manifests

###### Auto generated by spf13/cobra on 27-Jun-2022