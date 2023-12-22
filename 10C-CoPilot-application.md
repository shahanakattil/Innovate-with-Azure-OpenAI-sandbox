# Deploy a Chat CoPilot application based on Semantic Kernal

## Task 1: Deployment of Chat CoPilot application

1. In the LabVM, click on **Start**, from the start menu search and select for **PowerShell 6**. 

1. Run the following command to change the path.

   ```
   cd C:\LabFiles\chat-copilot\scripts
   ```

1. Run the following to set the execution policy.

   ```
   Set-ExecutionPolicy -ExecutionPolicy Unrestricted -Scope Process
   ``` 

1. The execution policy helps protect you from scripts that you do not trust. Changing the execution policy might expose you to the security risks described in the about_Execution_Policies help topic. Do you want to change the execution policy?, enter **A** and hit **Enter**.

1. Configure Chat Copilot by running the following command.

   ```powershell
   .\Configure.ps1 -AIService AzureOpenAI -APIKey {API_KEY} -Endpoint {AZURE_OPENAI_ENDPOINT} -CompletionModel {CompletionModel_NAME} -EmbeddingModel {EmbeddingModel_NAME}
   ```

   - `API_KEY`: The `API key` for Azure OpenAI or OpenAI.
   - `AZURE_OPENAI_ENDPOINT`: The Azure OpenAI resource `Endpoint` address. Omit `-Endpoint` if using OpenAI.
   - `{CompletionModel_NAME}`: Deployment name of the `gpt-35-turbo` model.
   - `{EmbeddingModel_NAME}`:  Deployment name of the `text-embedding-ada-002` model.
   - Execution will take 2 to 3 minutes.

1. Run Chat Copilot locally. This step starts the **backend API** application. frontend

   ```powershell
   .\Start-Backend.ps1
   ```
   
   > **Note:** It may take a few minutes for Yarn packages to install on the first run.

1. Open another tab in **Edge**, in the browser window paste the following link, you should see a confirmation message: `Healthy`.

   ```powershell
   https://localhost:40443/healthz
   ```
  
   > **Note:** Don't close the powershell window keep it running up.

1. In the LabVM, click on **Start**, from the start menu search and select for **PowerShell 6**. 

1. Run the following command to change the path.

   ```
   cd C:\LabFiles\chat-copilot\scripts
   ```

1. Run the following to set the execution policy.

   ```
   Set-ExecutionPolicy -ExecutionPolicy Unrestricted -Scope Process
   ``` 

1. The execution policy helps protect you from scripts that you do not trust. Changing the execution policy might expose you to the security risks described in the about_Execution_Policies help topic. Do you want to change the execution policy?, enter **A** and hit **Enter**.

1. Configure **Chat Copilot** by running the following command.

   ```powershell
   .\Start-Frontend.ps1
   ```

   > **Note:** It may take a few minutes for Yarn packages to install on the first run.

1. Once the deployment of script is executed succeddedfully it will redirect to `http://localhost:3000/` Chat CoPilot in **Edge** browser. 

1. Now **Chat Copilot** application is ready to use you can ask any question Chat Copilot will response accoundingly.