---
title: Generate change logs from conventional commits
date: 2022-04-02
image: /assets/images/2021/code.jpg
---

We can generate change logs from our commits if we follow the priniciples of [conventional commits](https://www.conventionalcommits.org/en/v1.0.0-beta.4/).

We can use [standard-version](https://github.com/conventional-changelog/standard-version) to automatically generate change logs(uses conventional commits) and version our code(uses semver).

## Setup **standard-version**

1. Install standard-version

```bash
npm i --save-dev standard-version
```

2. Add release script in **package.json**

```json
{
    "scripts": {
        "release": "standard-version"
    }
}
```

3. Generate first release

```bash
npm run release -- --first-release
```

4. For subsequent releases

```bash
npm run release
# can add **tags** option to generate tag
```
