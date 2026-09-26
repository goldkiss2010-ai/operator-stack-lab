# Contributing

Contributions, bug reports, and small experimental extensions are welcome.

## Before proposing a change

Operator Stack Lab is intentionally lightweight: a static, dependency-free browser tool that makes the order and structure of image operations visible.

Please prefer changes that preserve these properties:

- no build step for the basic release
- no server requirement
- local image processing in the browser
- visually explicit operation order
- clear distinction between pointwise and spatial/stochastic operations
- transparent, approximate cost modeling rather than benchmark claims

## Bug reports

Please include:

1. browser and operating system
2. steps to reproduce
3. expected behavior
4. actual behavior
5. a screenshot when it helps explain a UI issue

Do not attach private or sensitive source images unless they are necessary and you have the right to share them.

## Pull requests

Keep changes focused. If adding a new operation, please document:

- whether it is pointwise, spatial, or stochastic
- its parameters and practical parameter ranges
- the function/operator actually implemented
- how its cost estimate is calculated
- any effect it has on transfer-curve or derivative displays

## License of contributions

By submitting a contribution, you agree that it may be distributed under the MIT License used by this repository.
