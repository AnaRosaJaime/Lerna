# Lerna template project

Template mono repository project multi packages using [Lerna](https://github.com/lerna/lerna), a tool for managing JavaScript projects with multiple packages.

## Requirements

Install Lerna globally
```
npm install --global lerna
```

## How it works

### Commands

The main commands in Lerna are `lerna boostrap` and `lerna publish`

**bootstrap**:

```
lerna bootstrap
```

Install all the package dependencies and links any cross-dependencies:

When run, this command will:
    1. npm install all external dependencies of each package.
    2. Symlink together all Lerna packages that are dependencies of each other.
    3. npm run prepublish in all bootstrapped packages.
    4. npm run prepare in all bootstrapped packages.

**publish**:

```
lerna publish
```

Before publishing, Lerna determinate if a package has to be published by checking if there is any change in the repo according to the last version of git repository. Attention! It is possible to generate different versions of the same package (without changes) if the changes of the package are not pushed in the repository before publishing it.

### devDependencies

The dev dependecies can be pulled up the root of repo *except those used by npm script*

Benefits:

- All packages use the same version of a given dependency
- Dependency installation time is reduced
- Less storage is needed

