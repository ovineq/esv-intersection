[![npm version](https://badge.fury.io/js/%40equinor%2Fesv-intersection.svg)](https://badge.fury.io/js/%40equinor%2Fesv-intersection)
![Publish Package](https://github.com/equinor/esv-intersection/workflows/Publish%20Package/badge.svg)
![Unit tests](https://github.com/equinor/esv-intersection/workflows/Unit%20tests/badge.svg)
# ESV Intersection component
A reusable component to create intersection visualizations for wells

Part of the [Equinor Subsurface Visualization project](https://github.com/equinor/esv)

- **Repository**: https://github.com/equinor/esv-intersection
- **NPM Package**: https://www.npmjs.com/package/@equinor/esv-intersection
- **Documentation (latest)**: https://equinor.github.io/esv-intersection/
- **Storybook (latest)**: https://equinor.github.io/esv-intersection/storybook/latest
- **Storybook (nightly)**: https://equinor.github.io/esv-intersection/storybook/master
- **React/typescript example**: https://github.com/equinor/react-intersection-example

## Getting started

#### Installation
Using npm:
```bash
npm install --save @equinor/esv-intersection
```
Using yarn:
```bash
yarn add @equinor/esv-intersection
```

#### Usage

```javascript
import { Controller, GridLayer } from '@equinor/esv-intersection';

const container = document.createElement('div');
const controller = new Controller(container);

// the controller initially has zero height
controller.adjustToSize(400, 400);

controller.addLayer(new GridLayer('grid'));
```
For more examples, check out our stories in our online [storybook](https://equinor.github.io/esv-intersection/storybook/latest).

## Technical choices

- **Compiler**: [Typescript](https://www.npmjs.com/package/typescript)
- **Module bundler**: [Rollup](https://www.npmjs.com/package/rollup)
- **Testing**: [Jest](https://www.npmjs.com/package/jest)
- **Documentation**: [TypeDoc](https://www.npmjs.com/package/typedoc)
- **Code compressor**: [Terser](https://www.npmjs.com/package/terser)
- **Miscellaneous**:
  - Architecture: A container component that holds several layers, specialized for the type of data and visualization they address (analogous to the VidEx-map component https://github.com/equinor/videx-map)
  - Browser support: Target Edge, Chrome, Firefox, Safari
  - Styling: To be defined. Possibly SCSS or Emotion
  - Testing:
    - linting and unit tests, with test coverage - run automatically on Github Actions
    - possibly snapshot tests at a later stage
    - later on simulation tests, depending on resources and requirements
  - Dependencies:
    - _d3_
    - each layer can include additional dependencies
  - Accessibility: investigate compliance with WCAG2.1 (poossibly automatically)
  - Publishing:
    - automated
    - both tagged releases (semantic versioning) and nightly


## Development methodology
- The _Product Owners_ of the Intersection component are @farzadfz and @thuve
- Development is driven by _user stories_, created and prioritized by developers and POs together
- User stories can be grouped into _milestones_. A milestone represents what is expected to be achieved in about 2 months of development
- The development team has _planning meetings_ with the POs once a week
- The development team has _daily standups_, POs participation is optional but very much encouraged
- Development relies on a _project board_ hosted on github (https://github.com/equinor/intersection/projects/1)
- During planning meetings, the `To do` column of the board is populated with user stories and tasks
- What is placed in the `To do` column is expected to be completed in 1 week of normal work
- At the developers discretion, a _technical planning meeting_ can be held after the planning
- During a _technical planning meeting_, current user stories and tasks can be discussed and potentially split into smaller tasks
- A _demo_ for the stakeholders will be held approximately every 4 weeks
  - Stakeholders for the _WellX_ and _REP_ projects (including the _REP reference user group_) should be invited to the demo

## Contribution

See the contribution [page](CONTRIBUTION.md)

### Storybook

```bash
npm run storybook
```

Run the Storybook on the local machine. The storybook relies on data stored in the [esv-intersection-data](https://github.com/equinor/esv-intersection-data) repository.
It is included here as a git submodule. It is advised to run `git submodule update` before starting the storybook, in order to be sure that the sample data is up-to-date.

If the error `Cannot find module './esv-intersection-data'` appears in the console, there is a high chance that the submodule with the data has not been cloned correctly. Running `git submodule update --init` should fix the issue


![Equinor Logo](resources/images/equinor-logo.png)
