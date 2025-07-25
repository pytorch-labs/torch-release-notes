
# Release Notes worksheet releng

The main goal of this process is to rephrase all the commit messages below to make them **clear and easy to read** by the end user. You should follow the following instructions to do so:

* **Please clean up and format commit titles to be readable by the general PyTorch user.** Make sure you're [following the guidance here](https://docs.google.com/document/d/14OmgGBr1w6gl1VO47GGGdwrIaUNr92DFhQbY_NEk8mQ/edit)! Your resulting notes must be consistent and easy to read.
* Please sort commits into the following categories (you should not rename the categories!), I tried to pre-sort these to ease your work, feel free to move commits around if the current categorization is not good.
* Anything that is not public facing needs to be removed.
* If anything is miscategorized/belongs to another domain, move it to `miscategorized.md`.
* Please scan through `miscategorized.md` and handle any commits that belong within your domain according to these instructions.
* We place a lot of emphasis on the “BC-breaking” and “deprecation” sections. Those should be where the most effort goes in. The “improvements” and “bug fixes” for Python API should be nice as well.
* Once you are finished, move this very file from `todo/` to `done/` and submit a pull request.

The categories below are as follows:

* BC breaking: All commits that are BC-breaking. These are the most important commits. If any pre-sorted commit is actually BC-breaking, do move it to this section. Each commit should contain a paragraph explaining the rational behind the change as well as an example for how to update user code [BC-Guidelines](https://docs.google.com/document/d/14OmgGBr1w6gl1VO47GGGdwrIaUNr92DFhQbY_NEk8mQ/edit#heading=h.a9htwgvvec1m).
* Deprecations: All commits introducing deprecation. Each commit should include a small example explaining what should be done to update user code.
* new_features: All commits introducing a new feature (new functions, new submodule, new supported platform etc)
* improvements: All commits providing improvements to existing feature should be here (new backend for a function, new argument, better numerical stability)
* bug fixes: All commits that fix bugs and behaviors that do not match the documentation
* performance: All commits that are added mainly for performance (we separate this from improvements above to make it easier for users to look for it)
* documentation: All commits that add/update documentation
* Developers: All commits that are not end-user facing but still impact people that compile from source, develop into pytorch, extend pytorch, etc
* not user facing: All commits that are not public end-user facing and hence should be dropped from the release notes

## releng
### bc breaking
### deprecation

- Removed Anaconda support in CI/CD ([#147789](https://github.com/pytorch/pytorch/pull/147789), [#152338](https://github.com/pytorch/pytorch/pull/152338), [#152431](https://github.com/pytorch/pytorch/pull/152431), [#152377](https://github.com/pytorch/pytorch/pull/152377), [#152433](https://github.com/pytorch/pytorch/pull/152433), [#147476](https://github.com/pytorch/pytorch/pull/147476), [#151035](https://github.com/pytorch/pytorch/pull/151035), [#152860](https://github.com/pytorch/pytorch/pull/152860), [#152702](https://github.com/pytorch/pytorch/pull/152702), [#154303](https://github.com/pytorch/pytorch/pull/154303), [#154309](https://github.com/pytorch/pytorch/pull/154309) )
- Removed CUDA 11.8 and 12.4 support in CI/CD ([#155509](https://github.com/pytorch/pytorch/pull/155509), [#154169](https://github.com/pytorch/pytorch/pull/154169), [#152362](https://github.com/pytorch/pytorch/pull/152362), [#155555](https://github.com/pytorch/pytorch/pull/155555), [#154893](https://github.com/pytorch/pytorch/pull/154893))

### new features

- Add support for CUDA 12.9 in CI/CD ([#154980](https://github.com/pytorch/pytorch/pull/154980), [#156630](https://github.com/pytorch/pytorch/pull/156630), [#155895](https://github.com/pytorch/pytorch/pull/155895), [#155799](https://github.com/pytorch/pytorch/pull/155799), [#155496](https://github.com/pytorch/pytorch/pull/155496), [#155340](https://github.com/pytorch/pytorch/pull/155340), [#155819](https://github.com/pytorch/pytorch/pull/155819), [#156108](https://github.com/pytorch/pytorch/pull/156108))
- Add support for ROCm 6.4 in CI/CD ([#151236](https://github.com/pytorch/pytorch/pull/151236), [#151345](https://github.com/pytorch/pytorch/pull/151345), [#151355](https://github.com/pytorch/pytorch/pull/151355), [#153253](https://github.com/pytorch/pytorch/pull/153253), [#156112](https://github.com/pytorch/pytorch/pull/156112))
- Move CI from ubuntu 20.04 images to ubuntu 22.04 and 24.04 ([#154437](https://github.com/pytorch/pytorch/pull/154437), [#154153](https://github.com/pytorch/pytorch/pull/154153), [#149142](https://github.com/pytorch/pytorch/pull/149142))
- Move CI to CUDA 12.8 ([#154004](https://github.com/pytorch/pytorch/pull/154004), [#152810](https://github.com/pytorch/pytorch/pull/152810), [#155087](https://github.com/pytorch/pytorch/pull/155087), [#148963](https://github.com/pytorch/pytorch/pull/148963))
- Enable CI on MI300 ([#150667](https://github.com/pytorch/pytorch/pull/150667), [#152133](https://github.com/pytorch/pytorch/pull/152133), [#148394](https://github.com/pytorch/pytorch/pull/148394), [#153134](https://github.com/pytorch/pytorch/pull/153134))
- Enable CI on H100 ([#153900](https://github.com/pytorch/pytorch/pull/153900), [#154562](https://github.com/pytorch/pytorch/pull/154562), [#153170](https://github.com/pytorch/pytorch/pull/153170), [#155861](https://github.com/pytorch/pytorch/pull/155861), [#155719](https://github.com/pytorch/pytorch/pull/155719), [#156429](https://github.com/pytorch/pytorch/pull/156429))
- Enable CD for Windows Arm64 ([#150310](https://github.com/pytorch/pytorch/pull/150310), [#152109](https://github.com/pytorch/pytorch/pull/152109), [#149850](https://github.com/pytorch/pytorch/pull/149850), [#152099](https://github.com/pytorch/pytorch/pull/152099))

### improvements

- Enable testing of Binary Docker builds in CI/CD ([#151483](https://github.com/pytorch/pytorch/pull/151483), [#151488](https://github.com/pytorch/pytorch/pull/151488), [#151489](https://github.com/pytorch/pytorch/pull/151489), [#151706](https://github.com/pytorch/pytorch/pull/151706))
- Add smoke test to validate nccl and cudnn versions in pypi packages ([#149885](https://github.com/pytorch/pytorch/pull/149885), [#150194](https://github.com/pytorch/pytorch/pull/150194))
- Update gcc11 to gcc13 in manylinux images ([#152825](https://github.com/pytorch/pytorch/pull/152825), [#152825](https://github.com/pytorch/pytorch/pull/152825), [#150635](https://github.com/pytorch/pytorch/pull/150635))
- Update to cmake 3.27.2 ([#154783](https://github.com/pytorch/pytorch/pull/154783), [#150549](https://github.com/pytorch/pytorch/pull/150549), [#153380](https://github.com/pytorch/pytorch/pull/153380))
- Enable Monitoring for performance tests ([#153452](https://github.com/pytorch/pytorch/pull/153452), [#153453](https://github.com/pytorch/pytorch/pull/153453), [#153454](https://github.com/pytorch/pytorch/pull/153454), [#153456](https://github.com/pytorch/pytorch/pull/153456))
- Improve benchmarking and performance testing on MacOS ([#151721](https://github.com/pytorch/pytorch/pull/151721), [#151747](https://github.com/pytorch/pytorch/pull/151747), [#151748](https://github.com/pytorch/pytorch/pull/151748), [#153897](https://github.com/pytorch/pytorch/pull/153897), [#155493](https://github.com/pytorch/pytorch/pull/155493), [#153897](https://github.com/pytorch/pytorch/pull/153897), [#155493](https://github.com/pytorch/pytorch/pull/155493))
- Fix vs2022 caused AVX512 illegal instruction issue. ([#153480](https://github.com/pytorch/pytorch/pull/153480))


### bug fixes
- [CI] Use `setup-python` from for Mac tests ([#155698](https://github.com/pytorch/pytorch/pull/155698))
- Checkout optional submodules when publishing a release tarball ([#156615](https://github.com/pytorch/pytorch/pull/156615))
- Fix MacOS MP hang in Python-3.12+ ([#155698](https://github.com/pytorch/pytorch/pull/155698))
- Fix static functions when using module in MSVC ([#148675](https://github.com/pytorch/pytorch/pull/148675))

### performance
### docs
- Migrate to new theme ([#149331](https://github.com/pytorch/pytorch/pull/149331))
### devs

### Untopiced

### not user facing
- [CI][docker] Use multistage build for triton ([#149413](https://github.com/pytorch/pytorch/pull/149413))
- [CI] Use system nccl in build ([#150226](https://github.com/pytorch/pytorch/pull/150226))
- Remove Ubuntu 18.04 scripts ([#149479](https://github.com/pytorch/pytorch/pull/149479))
- Remove outdated instructions from CI scripts ([#149795](https://github.com/pytorch/pytorch/pull/149795))
- Fix broken URLs ([#152237](https://github.com/pytorch/pytorch/pull/152237))
- Fix more URLs ([#153277](https://github.com/pytorch/pytorch/pull/153277))
- update torchvision pin ([#154255](https://github.com/pytorch/pytorch/pull/154255))
- Allow rebuild of triton on workflow_dispatch ([#149865](https://github.com/pytorch/pytorch/pull/149865))
- [CI] enable operator benchmark on CPU ([#143733](https://github.com/pytorch/pytorch/pull/143733))
- Update the baseline for max_autotune ci workflow ([#149107](https://github.com/pytorch/pytorch/pull/149107))
- Remove a workaround added in #149381 ([#150693](https://github.com/pytorch/pytorch/pull/150693))
- [Proposal] Drop legacy CUDA support to slim down the wheels ([#152069](https://github.com/pytorch/pytorch/pull/152069))
- Update to using mypy 1.15 ([#154054](https://github.com/pytorch/pytorch/pull/154054))
- Bump pillow from 10.0.1 to 10.3.0 in /.github/requirements (8f08f90b61f)
- [BE][AOTI] Remove duplicate schema for ExternKernelNode ([#155867](https://github.com/pytorch/pytorch/pull/155867))
- [benchmarking] Inc aarch64 bench shards to 15 ([#152324](https://github.com/pytorch/pytorch/pull/152324))
- mypy 1.16.0 ([#155821](https://github.com/pytorch/pytorch/pull/155821))
- Bump requests from 2.32.2 to 2.32.4 in /.github (05faba40287)
- Provide access to the cudaGraph_t underlying a CUDAGraph. ([#155164](https://github.com/pytorch/pytorch/pull/155164))
- Improve error handling if nvcc is not found ([#148671](https://github.com/pytorch/pytorch/pull/148671))
- Add ninja to requirements-ci for all arch ([#148778](https://github.com/pytorch/pytorch/pull/148778))
- [AOTI] Re-enable AOTI cpp unit test ([#149085](https://github.com/pytorch/pytorch/pull/149085))
- ci: Fix check_binary gcc abi check ([#149104](https://github.com/pytorch/pytorch/pull/149104))
- ci: Update linux_job references to v2 ([#149102](https://github.com/pytorch/pytorch/pull/149102))
- [ez] Flush trymerge print statements ([#149012](https://github.com/pytorch/pytorch/pull/149012))
- cd: Add no-cache for test binaries ([#149218](https://github.com/pytorch/pytorch/pull/149218))
- [EZ][BE] Remove cross-compilation options from mac-build.yml ([#149237](https://github.com/pytorch/pytorch/pull/149237))
- Upgrade to CUDA 12.8.1 for nightly binaries ([#152923](https://github.com/pytorch/pytorch/pull/152923))
- Use almalinux docker files for building Magma ([#152358](https://github.com/pytorch/pytorch/pull/152358))
- [ROCm] Use alternate mirror for drm repo ([#149380](https://github.com/pytorch/pytorch/pull/149380))
- [EZ][Docker] Remove `install_db.sh` ([#149360](https://github.com/pytorch/pytorch/pull/149360))
- Enable more nightly tests on s390x ([#148452](https://github.com/pytorch/pytorch/pull/148452))
- [audio hash update] update the pinned audio hash ([#149467](https://github.com/pytorch/pytorch/pull/149467))
- [executorch hash update] update the pinned executorch hash ([#147422](https://github.com/pytorch/pytorch/pull/147422))
- Improve docker build cleanup on s390x runners ([#149316](https://github.com/pytorch/pytorch/pull/149316))
- Document patched podman build for s390x runners ([#147618](https://github.com/pytorch/pytorch/pull/147618))
- Update s390x docker image ([#148444](https://github.com/pytorch/pytorch/pull/148444))\
- [CI][docker] Remove vulkan and swiftshader from docker builds ([#149530](https://github.com/pytorch/pytorch/pull/149530))
- Update nightly s390x builds ([#149337](https://github.com/pytorch/pytorch/pull/149337))
- [executorch hash update] update the pinned executorch hash ([#149585](https://github.com/pytorch/pytorch/pull/149585))
- [CI] Fix xpu linux test permission issue and add ci docker image pull ([#149053](https://github.com/pytorch/pytorch/pull/149053))
- [ROCm] Update libamd_comgr.so file in triton wheel build ([#149855](https://github.com/pytorch/pytorch/pull/149855))
- [Test] Add simple MPS op benchmarks ([#149914](https://github.com/pytorch/pytorch/pull/149914))
- [BE][CI] Update configure-aws-credential to v4 ([#149918](https://github.com/pytorch/pytorch/pull/149918))
- [CI][BE] Update other actions ([#149922](https://github.com/pytorch/pytorch/pull/149922))
- [BE][CI] Update actionlint to 1.7.7 ([#149919](https://github.com/pytorch/pytorch/pull/149919))
- Add XPU and SYCL Merge Patterns ([#149933](https://github.com/pytorch/pytorch/pull/149933))
- [CI] Add MacOS-M2-15 as MPS test target on trunk ([#149900](https://github.com/pytorch/pytorch/pull/149900))
- cd: Restore windows release builds for libtorch ([#149863](https://github.com/pytorch/pytorch/pull/149863))
- Skip cxxabi check for s390x ([#149954](https://github.com/pytorch/pytorch/pull/149954))
- Switch s390x tests to blocklist ([#149507](https://github.com/pytorch/pytorch/pull/149507))
- Refactor cudnn version check in smoke test for Windows ([#150015](https://github.com/pytorch/pytorch/pull/150015))
- Newer conda versions require --update-deps to update dependencies such as libgcc-ng ([#149599](https://github.com/pytorch/pytorch/pull/149599))
- Delete linux-focal-cuda12_6-py3_10-gcc11-bazel-test ([#150066](https://github.com/pytorch/pytorch/pull/150066))
- [CI] Fix log artifact not containing test logs? ([#149577](https://github.com/pytorch/pytorch/pull/149577))
- [ROCm] use magma-rocm tarball for CI/CD ([#149986](https://github.com/pytorch/pytorch/pull/149986))
- [ROCm][CI] Increase wheel build timeout from 210 to 240 ([#150221](https://github.com/pytorch/pytorch/pull/150221))
- [BE] Get rid of cross-compile and x86 build options for Mac ([#150362](https://github.com/pytorch/pytorch/pull/150362))
- [CI] Fix log artifact not containing test logs attempt 2 ([#150234](https://github.com/pytorch/pytorch/pull/150234))
- [ez] Remove dead lite interpreter CI code ([#150424](https://github.com/pytorch/pytorch/pull/150424))
- Update torch.compile issue template ([#150192](https://github.com/pytorch/pytorch/pull/150192))
- ci: Use cache / progress when local docker build ([#150551](https://github.com/pytorch/pytorch/pull/150551))
- Add Chillee as core reviewer ([#150579](https://github.com/pytorch/pytorch/pull/150579))
- Enable weekly test for operator benchmark  ([#150502](https://github.com/pytorch/pytorch/pull/150502))
- [audio hash update] update the pinned audio hash ([#150589](https://github.com/pytorch/pytorch/pull/150589))
- [executorch hash update] update the pinned executorch hash ([#149817](https://github.com/pytorch/pytorch/pull/149817))
- Use 'rocm' naming for rocm-related workflows/jobs ([#150555](https://github.com/pytorch/pytorch/pull/150555))
- [xla hash update] update the pinned xla hash ([#132021](https://github.com/pytorch/pytorch/pull/132021))
- [CI] Add XPU compiled check in CICD ([#150771](https://github.com/pytorch/pytorch/pull/150771))
- [executorch hash update] update the pinned executorch hash ([#150722](https://github.com/pytorch/pytorch/pull/150722))
- [executorch hash update] update the pinned executorch hash ([#151195](https://github.com/pytorch/pytorch/pull/151195))
- [executorch hash update] update the pinned executorch hash ([#151280](https://github.com/pytorch/pytorch/pull/151280))
- Action for building docker binary builds ([#151471](https://github.com/pytorch/pytorch/pull/151471))
- [executorch hash update] update the pinned executorch hash ([#151493](https://github.com/pytorch/pytorch/pull/151493))
- Update docker image names for s390x ([#151426](https://github.com/pytorch/pytorch/pull/151426))
- Add automatic categorization for release notes: inductor (aoti) ([#151569](https://github.com/pytorch/pytorch/pull/151569))
- [executorch hash update] update the pinned executorch hash ([#151632](https://github.com/pytorch/pytorch/pull/151632))
- Replace perf-nightly-macos with inductor-perf-nightly-macos ([#151698](https://github.com/pytorch/pytorch/pull/151698))
- Add OIDC permissions to xpu workflow ([#151455](https://github.com/pytorch/pytorch/pull/151455))
- [BE] Move aarch64 docker build to larger node ([#151808](https://github.com/pytorch/pytorch/pull/151808))
- [MergeBot] Update PullRequestResolved Regex ([#151814](https://github.com/pytorch/pytorch/pull/151814))
- Ensure runners have the required prefix ([#151815](https://github.com/pytorch/pytorch/pull/151815))
- Add dates to pages ([#151602](https://github.com/pytorch/pytorch/pull/151602))
- [audio hash update] update the pinned audio hash ([#151729](https://github.com/pytorch/pytorch/pull/151729))
- [CI] Remove protobuf from docker image ([#151933](https://github.com/pytorch/pytorch/pull/151933))
- [CI][docker] Use install_cusparselt when possible in docker image  ([#150600](https://github.com/pytorch/pytorch/pull/150600))
- Pin theme to a branch ([#152046](https://github.com/pytorch/pytorch/pull/152046))
- [audio hash update] update the pinned audio hash ([#152149](https://github.com/pytorch/pytorch/pull/152149))
- [executorch hash update] update the pinned executorch hash ([#151728](https://github.com/pytorch/pytorch/pull/151728))
- Add scripts to check xrefs and urls ([#151844](https://github.com/pytorch/pytorch/pull/151844))
- [xla hash update] update the pinned xla hash ([#151210](https://github.com/pytorch/pytorch/pull/151210))
- Pin to SHA for actions outside of PyTorch ([#152110](https://github.com/pytorch/pytorch/pull/152110))
- Add a label to skip URL lint if needed ([#152340](https://github.com/pytorch/pytorch/pull/152340))
- Remove unused Manylinux2014 Docker files and builds ([#152428](https://github.com/pytorch/pytorch/pull/152428))
- Run link checks on modified files on push too ([#152464](https://github.com/pytorch/pytorch/pull/152464))
- [CI][CD] Unify install_cuda and install_cuda_aarch64 scripts ([#152140](https://github.com/pytorch/pytorch/pull/152140))
- [ROCm] add almalinux images ([#152492](https://github.com/pytorch/pytorch/pull/152492))
- Remove dead binary_ios_build, test, upload scripts ([#152461](https://github.com/pytorch/pytorch/pull/152461))
- [ROCm] Use almalinux docker files for building Magma ([#152488](https://github.com/pytorch/pytorch/pull/152488))
- 🐛 Add `ciflow/pull`🦋 ([#152567](https://github.com/pytorch/pytorch/pull/152567))
- removing short-perf-test-cpu.sh and short-perf-test-gpu.sh ([#152551](https://github.com/pytorch/pytorch/pull/152551))
- Add parameters for monitor  ([#152541](https://github.com/pytorch/pytorch/pull/152541))
- Improve error wording in _link_check.yml ([#152726](https://github.com/pytorch/pytorch/pull/152726))
- Rename "startup-tracing-compile" to "compile-time" in label_to_label.yml ([#152711](https://github.com/pytorch/pytorch/pull/152711))
- [xla hash update] update the pinned xla hash ([#152809](https://github.com/pytorch/pytorch/pull/152809))
- [CI] docker images use tags instead of image name ([#152209](https://github.com/pytorch/pytorch/pull/152209))
- Use three-dot diffs in URL and xref lint workflows ([#152895](https://github.com/pytorch/pytorch/pull/152895))
- Run url and xref linters independently ([#152899](https://github.com/pytorch/pytorch/pull/152899))
- [audio hash update] update the pinned audio hash ([#152885](https://github.com/pytorch/pytorch/pull/152885))
- Fix conditional git diff in _link_check.yml ([#152919](https://github.com/pytorch/pytorch/pull/152919))
- [CI] Upgrade sccache to 0.10.0 ([#152957](https://github.com/pytorch/pytorch/pull/152957))
- Pass UNINSTALL_DILL to docker build ([#152792](https://github.com/pytorch/pytorch/pull/152792))
- [Testing] Add logic for running MPS tests ([#153012](https://github.com/pytorch/pytorch/pull/153012))
- Run URL linter on nightly only ([#153157](https://github.com/pytorch/pytorch/pull/153157))
- [CI] Increase shards number for XPU ci UT tests ([#149113](https://github.com/pytorch/pytorch/pull/149113))
- Skip lintchecks for now ([#153156](https://github.com/pytorch/pytorch/pull/153156))
- Allow workflows to opt-out of experiments ([#153085](https://github.com/pytorch/pytorch/pull/153085))
- [BE][CI] Merge regular and MPS test config shards ([#152719](https://github.com/pytorch/pytorch/pull/152719))
- [CI] Enable XCCL in XPU CI build ([#150927](https://github.com/pytorch/pytorch/pull/150927))
- Stop uploading sccache stats to benchmark database ([#153285](https://github.com/pytorch/pytorch/pull/153285))
- [BE] Delete now unused `mac-mps.yml` ([#153263](https://github.com/pytorch/pytorch/pull/153263))
- [audio hash update] update the pinned audio hash ([#153301](https://github.com/pytorch/pytorch/pull/153301))
- [executorch hash update] update the pinned executorch hash ([#152238](https://github.com/pytorch/pytorch/pull/152238))
- Opt-out LF runners from of inductor jobs ([#153151](https://github.com/pytorch/pytorch/pull/153151))
- [xla hash update] update the pinned xla hash ([#153368](https://github.com/pytorch/pytorch/pull/153368))
- [CI] Collect accuracy for MPS inductor benchmarks ([#153443](https://github.com/pytorch/pytorch/pull/153443))
- Fix AOTI cpp tests ([#153423](https://github.com/pytorch/pytorch/pull/153423))
- Add matching against hypothetical (new) ghstack pull-request trailer ([#153528](https://github.com/pytorch/pytorch/pull/153528))
- [audio hash update] update the pinned audio hash ([#153507](https://github.com/pytorch/pytorch/pull/153507))
- Change aoti cpp tests to run serially within file ([#152960](https://github.com/pytorch/pytorch/pull/152960))
- [BE] Upgrade XPU support package to 2025.1 in CICD ([#151899](https://github.com/pytorch/pytorch/pull/151899))
- [ez][CI] Add linux aarch64 to upload test stats, change format of trigger for upload test stats ([#153505](https://github.com/pytorch/pytorch/pull/153505))
- [ez][trymerge] Edit revert message for reverted ghstack PRs ([#153573](https://github.com/pytorch/pytorch/pull/153573))
- Change trigger for autoformat, use --all-files ([#153289](https://github.com/pytorch/pytorch/pull/153289))
- codecache: Remove cpp_prefix.h duplication per build, then precompile it ([#144293](https://github.com/pytorch/pytorch/pull/144293))
- [xla hash update] update the pinned xla hash ([#153816](https://github.com/pytorch/pytorch/pull/153816))
- [BE][EZ] Delete unsued conda-env-IOS.txt ([#153849](https://github.com/pytorch/pytorch/pull/153849))
- Bump triton pin for the release 3.3.1 of triton ([#153951](https://github.com/pytorch/pytorch/pull/153951))
- s390x: use qemu issue workaround for runner registration too ([#154030](https://github.com/pytorch/pytorch/pull/154030))
- Follow up to #152209, remove compat patch after docker image rename ([#152958](https://github.com/pytorch/pytorch/pull/152958))
- S390x update docker image ([#153619](https://github.com/pytorch/pytorch/pull/153619))
- Update CPU Inductor merge rules by adding more CPP Template ([#152086](https://github.com/pytorch/pytorch/pull/152086))
- Update GH action to use the correct label ([#154126](https://github.com/pytorch/pytorch/pull/154126))
- [audio hash update] update the pinned audio hash ([#154001](https://github.com/pytorch/pytorch/pull/154001))
- Enable AArch64 CI scripts to be used for local dev ([#143190](https://github.com/pytorch/pytorch/pull/143190))
- Disable cache and utilization stats uploading steps on s390x ([#150297](https://github.com/pytorch/pytorch/pull/150297))
- [BE][CI] Update expecttest version to 0.3.0 ([#154237](https://github.com/pytorch/pytorch/pull/154237))
- Add sitemap ([#154158](https://github.com/pytorch/pytorch/pull/154158))
- [BE] Delete unused pip-requirements-iOS.txt ([#154271](https://github.com/pytorch/pytorch/pull/154271))
- Re-enable link linter ([#153280](https://github.com/pytorch/pytorch/pull/153280))
- [CI] Update MacOS numba and scipy versions ([#154269](https://github.com/pytorch/pytorch/pull/154269))
- [CI] Update MacOS conda requirmenets ([#154270](https://github.com/pytorch/pytorch/pull/154270))
- [mergebot] Do not block on autoformat workflow ([#154236](https://github.com/pytorch/pytorch/pull/154236))
- [BE] Don't run windows builds in pull.yml ([#154264](https://github.com/pytorch/pytorch/pull/154264))
- [CI] Reuse old whl on more workflows ([#154285](https://github.com/pytorch/pytorch/pull/154285))
- [CI] Move Mac testing to 3.12 ([#154177](https://github.com/pytorch/pytorch/pull/154177))
- Bump protobuf version and refactor tensorboard tests ([#154244](https://github.com/pytorch/pytorch/pull/154244))
- [BE] Sort requirements files alphabetically ([#154304](https://github.com/pytorch/pytorch/pull/154304))
- [CI] Do not install libuv on MacOS ([#154307](https://github.com/pytorch/pytorch/pull/154307))
- [ONNX] Update onnx to 1.18 ([#153746](https://github.com/pytorch/pytorch/pull/153746))
- [BE] Do not templetize unnnecessarily ([#154305](https://github.com/pytorch/pytorch/pull/154305))
- Almalinux image, install glibc-langpack-en ([#154364](https://github.com/pytorch/pytorch/pull/154364))
- Pin almalinux version to 8.10-20250519 ([#154367](https://github.com/pytorch/pytorch/pull/154367))
- [BE] Refactor manywheel build scripts ([#154372](https://github.com/pytorch/pytorch/pull/154372))
- update torchbench pin ([#154256](https://github.com/pytorch/pytorch/pull/154256))
- [BE][CI][Easy] Run `lintrunner` on generated `.pyi` stub files ([#150732](https://github.com/pytorch/pytorch/pull/150732))
- Create issue template: Release highlight for proposed Feature ([#154125](https://github.com/pytorch/pytorch/pull/154125))
- [CI] Update torchbench pin ([#154453](https://github.com/pytorch/pytorch/pull/154453))
- Fix the logic of set_cpu_affinity ([#154503](https://github.com/pytorch/pytorch/pull/154503))
- [CI] Pin the torchao version used when testing torchbench ([#154723](https://github.com/pytorch/pytorch/pull/154723))
- [Binary-builds]Use System NCCL by default in CI/CD. ([#152835](https://github.com/pytorch/pytorch/pull/152835))
- [ONNX] Simplify onnx test dependencies ([#154732](https://github.com/pytorch/pytorch/pull/154732))
- [ez][CI] Do not reuse old whl if deleting files ([#154731](https://github.com/pytorch/pytorch/pull/154731))
- [ez][CI] Reuse old whl: remove old zip/whl ([#154770](https://github.com/pytorch/pytorch/pull/154770))
- [upstream triton] support build with setup.py in ./python/ or in ./ ([#154635](https://github.com/pytorch/pytorch/pull/154635))
- [Submodule] Bump flatbuffers to v24.12.23 ([#143964](https://github.com/pytorch/pytorch/pull/143964))
- [audio hash update] update the pinned audio hash ([#154776](https://github.com/pytorch/pytorch/pull/154776))
- [ez][TD] Fix TD indexer workflow ([#154868](https://github.com/pytorch/pytorch/pull/154868))
- [CI] Reuse old whl: replace the version ([#154773](https://github.com/pytorch/pytorch/pull/154773))
- [CI] Reuse old whl on PRs ([#154662](https://github.com/pytorch/pytorch/pull/154662))
- Move remaining CI jobs to VS 2022 ([#154811](https://github.com/pytorch/pytorch/pull/154811))
- Add option to define OpenBLAS version for manylinux Dockerfile_2_28_aarch64 ([#150106](https://github.com/pytorch/pytorch/pull/150106))
- Update bug-report.yml ([#154857](https://github.com/pytorch/pytorch/pull/154857))
- Update merge_rules.yaml ([#155008](https://github.com/pytorch/pytorch/pull/155008))
- add JSON output support for operator benchmark ([#154410](https://github.com/pytorch/pytorch/pull/154410))
- Enable check_gomp for Ubuntu OSes ([#155119](https://github.com/pytorch/pytorch/pull/155119))
- Workflow to tag trunk commits with `trunk/{commit-sha}` tags ([#155170](https://github.com/pytorch/pytorch/pull/155170))
- Enable CPP Extension Open Registration tests on Arm ([#144774](https://github.com/pytorch/pytorch/pull/144774))
- [ROCm] manywheel missing hipsparselt deps ([#155254](https://github.com/pytorch/pytorch/pull/155254))
- [CI] fix xpu-smi hang issue on some xpu runners ([#155194](https://github.com/pytorch/pytorch/pull/155194))
- Reduce scope of s390x CI ([#155208](https://github.com/pytorch/pytorch/pull/155208))
- [CI]Update windows runner to windows-2022 ([#154368](https://github.com/pytorch/pytorch/pull/154368))
- [ROCm] fix nightly wheel, second attempt ([#155388](https://github.com/pytorch/pytorch/pull/155388))
- [CI] remove xfail sm89 job ([#155244](https://github.com/pytorch/pytorch/pull/155244))
- [BE]: Update cusparselt to 0.7.1 ([#155232](https://github.com/pytorch/pytorch/pull/155232))
- Fix sqlite3 in x86 Docker container. ([#155211](https://github.com/pytorch/pytorch/pull/155211))
- [CI] Fix XPU runner setup status issue ([#155443](https://github.com/pytorch/pytorch/pull/155443))
- [Easy] update pip sources for ROCm in nightly pull tool ([#145685](https://github.com/pytorch/pytorch/pull/145685))
- [XPU] Split triton version as 2 files to decouple triton version bump ([#155313](https://github.com/pytorch/pytorch/pull/155313))
- [ez][CI] Reuse old whl: turn off on releases, add docs files to ok list ([#155346](https://github.com/pytorch/pytorch/pull/155346))
- [CI] Set PATH during build to include location of sccache wrapped nvcc ([#155464](https://github.com/pytorch/pytorch/pull/155464))
- [xla hash update] update the pinned xla hash ([#154348](https://github.com/pytorch/pytorch/pull/154348))
- Reapply "Cleanup VS 2019 refs in pytorch (#145863)" (#152613) ([#155478](https://github.com/pytorch/pytorch/pull/155478))
- [CI] Move tlparse to requirements files ([#155601](https://github.com/pytorch/pytorch/pull/155601))
- Add helion x pt2 test ([#155513](https://github.com/pytorch/pytorch/pull/155513))
- [BE] Update the XPU support package to 2025.1.3 ([#154346](https://github.com/pytorch/pytorch/pull/154346))
- [CI] Use `setup-python` from test-infra to do MacOS builds ([#155515](https://github.com/pytorch/pytorch/pull/155515))
- [CI] Disable ET tests ([#155708](https://github.com/pytorch/pytorch/pull/155708))
- [CI] Move setuptools requirements from conda to pip ([#155697](https://github.com/pytorch/pytorch/pull/155697))
- Update XLA pin ([#155471](https://github.com/pytorch/pytorch/pull/155471))
- [trymerge] Error on ghstack commit with multiple PRs ([#154941](https://github.com/pytorch/pytorch/pull/154941))
- [CI] Reuse old whl: switch default to always ([#155572](https://github.com/pytorch/pytorch/pull/155572))
- Run tests on Amazon EC2 M8g Instances ([#153940](https://github.com/pytorch/pytorch/pull/153940))
- Switch to miniconda for ROCm CI ([#155239](https://github.com/pytorch/pytorch/pull/155239))
- [BE] Don't run the same tests on 2xlarge and 4xlarge ([#155859](https://github.com/pytorch/pytorch/pull/155859))
- [xla hash update] update the pinned xla hash ([#155779](https://github.com/pytorch/pytorch/pull/155779))
- [CI] Reuse old whl: track why failed to use the old whl ([#155860](https://github.com/pytorch/pytorch/pull/155860))
- [BE]: Update NCCL to 2.27.3 ([#155233](https://github.com/pytorch/pytorch/pull/155233))
- [executorch hash update] update the pinned executorch hash ([#156007](https://github.com/pytorch/pytorch/pull/156007))
- [audio hash update] update the pinned audio hash ([#155648](https://github.com/pytorch/pytorch/pull/155648))
- [xla hash update] update the pinned xla hash ([#156064](https://github.com/pytorch/pytorch/pull/156064))
- Remove unused Azure pipeline trigger script ([#156134](https://github.com/pytorch/pytorch/pull/156134))
- [CI] Move ASAN jobs to clang-18 ([#149099](https://github.com/pytorch/pytorch/pull/149099))
- [BE] fix typos in .ci/, .circleci/, .github/ ([#156069](https://github.com/pytorch/pytorch/pull/156069))
- [CI] Fix triton version split issue ([#155670](https://github.com/pytorch/pytorch/pull/155670))
- [audio hash update] update the pinned audio hash ([#156259](https://github.com/pytorch/pytorch/pull/156259))
- [CI] fix the ci image name for public copy in ghcr ([#156169](https://github.com/pytorch/pytorch/pull/156169))
- Skip more tests on s390x ([#155210](https://github.com/pytorch/pytorch/pull/155210))
- Integrated AMD AWS runners into Pytorch CI ([#153704](https://github.com/pytorch/pytorch/pull/153704))
- [Intel GPU] Update xpu triton commit pin for PyTorch release 2.8. ([#154194](https://github.com/pytorch/pytorch/pull/154194))
- Use linux.2xlarge runner ([#156351](https://github.com/pytorch/pytorch/pull/156351))
- [CI] fix xpu-smi hang in XPU test container ([#156171](https://github.com/pytorch/pytorch/pull/156171))
- [CI] Reuse old whl: loosen check for deleted files, do not handle renames ([#156138](https://github.com/pytorch/pytorch/pull/156138))

### security
