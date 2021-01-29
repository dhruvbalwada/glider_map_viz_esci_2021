# Notebooks Don Copy

This folder is Don's copy of Dhruv's  notebooks

## Data

Data currently lives in `glider-panel-demo` repository, so first to run the notebooks, we need to clone that data.

1. Clone `glider-panel-demo` repo outside of the `glider_map_viz_esci_2021` repo.

    ```bash
    # This example, clones the repo in desktop
    cd ~/Desktop
    git clone https://github.com/dhruvbalwada/glider-panel-demo.git
    ```

2. Softlink data into the `notebooks/don` folder so if there are data change, we can just pull from the `glider-panel-demo`.

    ```bash
    cd ~/GitRepos/GitHub/glider_map_viz_esci_2021/notebooks/don
    ln -s ~/Desktop/glider-panel-demo/data ./data
    ```
