# Reproducing `shamefully-hoist` Configuration Bug in pnpm

This repository is dedicated to replicating a bug associated with the `shamefully-hoist` configuration in pnpm.

## Steps to Reproduce:

1. Execute the following command:
    ```bash
    pnpm install
    ```

## Bug Description:

Upon inspecting the `node_modules` directory, a noticeable discrepancy is observed. Specifically, the `react-native-svg` package has a dependency on `css-select` with version ^2.1.0, yet it is erroneously linked to `css-select` version 4.3.0. This inconsistency stems from the fact that `node-html-parser` has a dependency on `css-select` version 4.3.0.

While the `.pnpm` virtual store correctly indexes the dependencies, the use of `shamefully-hoist` to symlink all packages to `node_modules` results in an incorrect indexing.

## Additional Information:

Feel free to explore the source code and configurations within this repository to gain further insights into the bug and its reproduction. Contributions and potential solutions are welcomed.
