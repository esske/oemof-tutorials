# oemof-tutorials

Welcome to the **oemof Tutorials** repository!  
These tutorials are designed to help you learn and apply different aspects of the oemof community packages. They range from beginner-friendly introductions to deep dives into how multiple oemof packages work together.

The workshops are provided as **Jupyter Books**, which you can:

*   access online and 
*   download as Jupyter Notebooks to explore and experiment with the material locally.

## Contribute

We warmly welcome contributions of all kinds!  
You can help by providing feedback, fixing typos, improving explanations, or adding new tutorial sections.

To contribute:

1.  **Fork** this repository.
2.  Commit your improvements.
3.  Open a **pull request**.

We appreciate your support in improving the tutorials.

## Build the Documentation Locally

If you want to build the documentation on your machine, you need to install the **Jupyter Book dependencies**.  
Please refer to the official installation guide:  
<https://jupyterbook.org/en/stable/start/overview.html#install-jupyter-book>

> **Important:** Make sure you install **jupyter-book < v2**, as newer versions are not yet supported in this project.

Once installed, you can build the HTML documentation from the root directory of your local clone:

```bash
jupyter-book build ./<tutorial>/
```

This will generate the HTML output in the `_build/html` folder.

## [LICENSE](LICENSE)