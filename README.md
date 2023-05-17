# Github Actions w/ Parallelization

## [Link to Scribe](https://scribehow.com/shared/Github_Actions_wParallelization__mr9an2-PSNqWHJVF0l3PcA)

## Important
This project **DOES NOT** include the following: 
- Package manager 
- Cypress dev dependency in package.json
## Project Setup
1. Create a new repository on Github by **forking** this repo. Ensure that this repository is one that you have full ownership over and is not owned by the organization. 
2. **Clone** the newly created repo on to your local machine.
3. Initialize the package manager of your choice 
    ```
    npm init or yarn init or pnpm init
    ```
4. Install Cypress and save it as a dev dependency
    ```
    npm i -D cypress or npm i -D cypress@x.x.x 
    (Be sure to use the same command as your package manager)
    ```
5. Navigate to your project folder in the terminal. Then create the directories below. The first directory should be added to the root project folder. In the final directory, create a YAML file.
    ```
    mkdir .github
    cd .github
    mkdir workflows
    cd workflows
    touch test.yml (Adapt file name as appropriate)
    ```
6. Open your project in the code editor of your choice (this example uses Visual Studio Code). 
    ```
    cd ../../
    code .
    ```
7. In your code editor, navigate to the `test.yml` file and add the Github Actions configuration with Parallelization outlined in this repo on the [package.json](https://github.com/jbeck-007/Github-Actions/blob/main/package.json) file.
8. Navigate to Cypress Cloud and create a new project. Give the project a name. On the next screen, copy the `Project Id`. 
    ![](https://colony-recorder.s3.amazonaws.com/files/2023-05-01/71990244-d901-437f-b241-89a4352164f9/stack_animation.webp)
    
9. Navigate to your Github repo. Click on Settings, then Secrets and variables, and then Actions. Click New Repository Secret and name it `PROJECT_ID`. Paste the project id you copied in the last step and then click Add Secret. 

    ![](https://colony-recorder.s3.amazonaws.com/files/2023-05-01/4e61d2ca-9c8b-4ad1-8fe7-c1b2cb713196/stack_animation.webp)

10. Navigate back to the Cypress Cloud and copy the `record key`. 

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-05-01/3988dcef-020c-4352-80de-eae8ec33bc28/user_cropped_screenshot.jpeg?tl_px=927,484&br_px=2420,1324&sharp=0.8&width=560&wat_scale=50&wat=1&wat_opacity=1&wat_gravity=northwest&wat_url=https://colony-recorder.s3.amazonaws.com/images/watermarks/EC4899_standard.png&wat_pad=262,139)

11. Navigate back to your Github repo. Click New Repository Secret and name it `CYPRESS_RECORD_KEY`. Paste the record key you copied in the last step and then click Add Secret. 

    ![](https://colony-recorder.s3.amazonaws.com/files/2023-05-01/07813813-1d60-4d37-880b-d423905fcfdb/stack_animation.webp)

12. Navigate back to your terminal window and run Cypress using the command below to setup Cloud recording. 
    ```
    npx cypress run --record --key <insert key here>
    ```
13. Navigate back to the Cypress Cloud window. Click on Project settings. Scroll down to the Github integration section. In the dropdown in the Github Repository section, select the repo for your project. Note that in order to see your repos, you must have previously registered your Github account in the Github integration for the entire organization. 

![](https://colony-recorder.s3.amazonaws.com/files/2023-05-01/093b356e-0199-4aae-b9ee-f45328c66e39/stack_animation.webp)

14. Navigate back to your code editor and ensure all changes have been saved. Then navigate to your terminal window and execute the following Git commands to commit and push your changes.
    ```
    git add .
    git commit -m "initial commit"
    git remote add origin <insert repo address here>
    git push --set-upstream origin main
    ```
15. You may now proceed with customizing the project to fit your specific use case. 




