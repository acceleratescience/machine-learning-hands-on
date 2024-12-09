# Contributing to our Machine Learning Hands On Page

We welcome contributions to our Machine Learning Hands On page. Contributions come in two forms:

1. **Project Content**: Follow these guidelines if you would like to upload a new project to the Machine Learning Hands On page.
2. **Site Contributions**: Follow these guidelines if you would like to contribute to the site itself.

## Making changes
The process for making changes is essentially the same for both types of contributions.

### Setting up
First, fork the repository and clone your version to your local machine (or you can use GitHub Codespaces).

For the sake of reproduciblity, we suggest using VSCode and the supplied devcontainer. When you open VSCode, or Codespaces, you should be prompted to open the folder in a container.

Create a new branch for your project in the form `add-project-<project-name>`. If you are not using the devcontainer, you will need to create a new python environment and install the dependencies in `requirements.txt`.

```bash
python3.11 -m venv venv
. venv/bin/activate
```

You can serve the website locally by running the following command:

```bash
mkdocs serve
```

### Formatting your project
Our websites are built using Material for Mkdocs, which uses markdown files to generate the content. Your content will go in the `docs/Projects` folder.

Your project can be in two forms: a Jupyter notebook or a markdown file.

#### Markdown
For markdown files, you can use the [Material for Mkdocs reference page](https://squidfunk.github.io/mkdocs-material/reference/) to format your content. We have no strict requirements for how your project should be formatted, but we suggest that you include the following sections:

1. **Introduction**: A brief overview of the project.
2. **Data**: A description of the dataset used in the project.
3. **Methods**: A description of the methods used in the project.
4. **Results**: A description of the results of the project.
5. **Conclusion**: A brief conclusion of the project.

This will be a public facing page, so please ensure that you have the rights to share any datasets or code that you include.

In order to view your page, you will need to add a link to your project in the `mkdocs.yml` file. You can add a new entry to the `nav` section, like so:

```yaml
nav:
  - Home:
    - Welcome!: index.md
    - License: Home/LICENSE.md
    - About us: Home/about.md
  - Projects:
    - Projects/index.md
    - Your Project: Projects/your_project.md
```

#### Jupyter Notebooks
If you have your project formatted in a Jupyter notebook, you can simply add the notebook to the `docs/Projects` folder. You will need to add a link to your project in the `mkdocs.yml` file, as described above, except you will link to the notebook file.

```yaml
nav:
  - Home:
    - Welcome!: index.md
    - License: Home/LICENSE.md
    - About us: Home/about.md
  - Projects:
    - Projects/index.md
    - Your Project: Projects/your_project.ipynb
```

#### Adding images
If you want to add images, then please add them to the `imgs` folder and reference them in your markdown file. For example, to add an image called `example.png`, you would use the following markdown:

```markdown
![image](./imgs/example.png)
```

You can also add more customizations to the image, using html:

```html
<img src="./imgs/example.png" alt="Example Image" style="width:800px;"/>
```

When you serve the website locally, you should see the image.

If you are using a Jupyter notebook, you can add images using the following code:

```markdown
![plot](../imgs/example.png)
```

The only difference here is that you need to go up one directory to find the `imgs` folder. You will not be able to see your images in the notebook, nor will you be able to see them when you serve the site locally. However, when you push your changes and the site is built, the images will be visible.

You should also add your project to the `Projects` directory in the root of the repository. This will allow others to download and run your project.

### Submitting your project
Once you have finished your project, you should push your changes and publish your branch. Then, create a pull request to the main repository using the provided template.

A reviewer will check your project and merge it into the main branch, or suggest changes.