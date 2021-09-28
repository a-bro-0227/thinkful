# Data Science curricula

All of the modules for programs in the Data Science domain!

This repo is broken down into 3 components:

1. The `/library` directory houses all of the checkpoints for all of the data programs.
    - Each checkpoint lives in a directory with a `content.md` file and any associated assets (like images, videos, etc).
    - Checkpoints are named in this format: `program_module_name_checkpoint_name`
        - If a checkpoint is general to several programs, there's no need for the PROGRAM prefix.
        - For ex
            - Program-specific: `data_science_orientation_learning_strategies`
            - General: `data_forms`
1. The `/modules` directory houses the YAML files that define a given module.
    - Modules translate to `content_bundles` when deployed.
    - Each module is composed of a set of checkpoints from the `/library` directory.
1. The `/programs` directory houses the YAML files that define a given program.
    - Each program is composed of a set of modules from the `/modules` directory.

To get started, refer to the templates in `/contributor_resources`:
- [Checkpoint template](https://github.com/Thinkful-Ed/web-dev-programs/blob/master/contributor_resources/checkpoint_template.md)
- [Module template](https://github.com/Thinkful-Ed/web-dev-programs/blob/master/contributor_resources/module_template.yaml)
- [Program template](https://github.com/Thinkful-Ed/web-dev-programs/blob/master/contributor_resources/program_template.yaml)

**A note on UUIDs:** If you're creating a new file, whether it's a checkpoint, module, or program, DO NOT ADD A UUID. The UUID will be added automatically by CircleCI. If you think your UUID should already exist somewhere, ask for help.

**Using the preview branch:**
- You can checkout how your content looks in the app by merging it into `origin/preview` and navigating to https://courses-preview.thinkful.com/ + the `content_bundle` slug. (For ex. https://courses-preview.thinkful.com/react-v1)
- NEVER MERGE PREVIEW INTO MASTER. The preview branch is volatile. Always use a feature branch to merge into both master and preview.
- Use the preview branch! If you're adding new content, make sure it looks right before you deploy it for students!

**Do not touch the following:**
- `/.circleci`
- `package.json`
- `package-lock.json`
- `.gitignore`

When in doubt, reach out to Kevin Pearce.

For requests to have a graphic designer make or redo an image, [use this form](https://form.asana.com/?hash=6a4d1bb0261edda3e030c7062cd8d2b7efd43fd48392fdeb492c5b8e2142cabf&id=1176892572482925). 
