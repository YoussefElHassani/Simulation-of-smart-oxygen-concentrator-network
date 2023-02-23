# Simulation of smart oxygen concentrator network
 
To run this project successfull, please follow the following instructions:

First, We need to create a virtual environment `venv`:

1. Open a terminal and navigate to the project directory.

2. Run the following command to create a virtual environment:
    ``` 
    python -m venv coding_challenge
    ```
    This will create a new virtual environment named myenv in the current directory.

3. Activate the virtual environment by running the following command:

    For linux systems:
    ``` 
    $ source coding_challenge/bin/activate
    ```

    For windows sytems:
    ``` 
    $ coding_challenge\Scripts\activate.ps1
    ```        

4. Install the required dependencies by running the following command:
    ``` 
    $ pip install -r requirements.txt
    ```       

5. Add a new kernel to your Jupyter config
    ``` 
    $ ipython kernel install --user --name=coding_challenge
    ``` 

6. Run the jupyter notebook using the following command, feel free to stop the server using CTRL+C
    ``` 
    $ jupyter notebook
    ``` 

7. When you're done working on the project, you can deactivate the virtual environment by running the following command:

    ``` 
    $ deactivate
    ```   