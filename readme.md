 # Deploying Your Agent Builder Project with a Custom Frontend
    2
    3 This guide will walk you through the process of deploying your Agent Builder project with a customizable React frontend
      using ChatKit, and deploying it on Vercel.
    4
    5 ## 1. Agent Builder Setup
    6
    7 First, you need to get your agent's workflow ID from Agent Builder.
    8
    9 1.  **Create and Publish Your Agent:**
   10     *   In [Agent Builder](https://agentbuilder.google.com/), create a new project.
   11     *   Once your agent is ready, publish and deploy it.
   12
   13 2.  **Get Your Workflow ID:**
   14     *   Go to the **</> Code** section of your deployed agent.
   15     *   Copy the **Workflow ID** and save it somewhere safe. You'll need it later.
   16
   17 ## 2. Sample App Setup
   18
   19 Next, set up the sample React application.
   20
   21 1.  **Clone the Sample App:**
   22     *   In Agent Builder, find the "Clone sample app" option (usually in the bottom right corner).
   23     *   Download the repository as a ZIP file.
   24
   25 2.  **Prepare the Project:**
   26     *   Extract the ZIP file and rename the folder to your liking.
   27     *   Open the project folder in your code editor.
   28
   29 3.  **Configure Environment Variables:**
   30     *   Create a new file named `.env` in the root of your project.
   31     *   Add your Workflow ID and OpenAI API key to the `.env` file like this:
      WORKFLOW_ID=your_workflow_id_here
      OPENAI_API_KEY=your_openai_api_key_here

    1
    2 ## 3. Theme Customization with ChatKit
    3
    4 Now, let's customize the look and feel of your chat interface.
    5
    6 1.  **Design Your Theme:**
    7     *   Go to the [ChatKit Studio Playground](https://chatkit.studio/playground).
    8     *   Customize the theme to match your desired style.
    9
   10 2.  **Copy the Theme Code:**
   11     *   Once you're happy with your theme, click the **</>** icon to view the code.
   12     *   Copy the `theme` object.
   13
   14 3.  **Apply the Theme:**
   15     *   In your project, open the file `src/components/ChatKitPanal.tsx`.
   16     *   Find the `theme` prop within the `<ChatKitPanel>` component.
   17     *   Paste the theme code you copied from the playground.
   18
   19 4.  **Test Locally:**
   20     *   Open your terminal and run the following command to see your customized chat app in action:
      npm run dev

   1
   2 ## 4. Deploy to Vercel
   3
   4 It's time to deploy your application to the web.
   5
   6 1.  **Install and Log in to Vercel CLI:**
   7     *   If you don't have the Vercel CLI, install it globally:
          npm install -g vercel
   1     *   Log in to your Vercel account (a browser window will open for authentication):
          vercel login

   1
   2 2.  **Deploy the Project:**
   3     *   Run the `vercel` command in your project's root directory:
          vercel

    1     *   You will be asked a series of questions. Follow these prompts:
    2         *   **Set up and deploy?** `[Y/n]` → Press **Enter** (for Yes).
    3         *   **Which scope do you want to deploy to?** → Select your Vercel username.
    4         *   **Link to existing project?** `[y/N]` → Press **N** (since this is the first deployment).
    5         *   **What's your project's name?** → Enter a name like `chatkit-app` or choose your own.
    6         *   **In which directory is your code located?** → Press **Enter** (for the current directory, `.`).
    7         *   **Want to modify these settings before deploying?** `[y/N]` → Press **N**.
    8
    9 ## 5. Final Configuration on Vercel
   10
   11 There are a couple of final steps to ensure your deployed app works correctly.
   12
   13 1.  **Add Environment Variables to Vercel:**
   14     *   Go to your project's settings on the Vercel dashboard.
   15     *   Navigate to the **Environment Variables** section.
   16     *   Add your `WORKFLOW_ID` and `OPENAI_API_KEY` just as you did in your local `.env` file.
   17     *   Redeploy your project for the changes to take effect.
   18
   19 2.  **Allowlist Your Domain in OpenAI:**
   20     *   Copy your Vercel project's URL (e.g., `https://your-project-name.vercel.app`).
   21     *   Go to your OpenAI organization settings: [Domain Allowlist](https:
      //platform.openai.com/settings/organization/security/domain-allowlist).
   22     *   Add your Vercel domain to the allowlist.
   23
   24 3.  **You're All Set!**
   25     *   Refresh your Vercel application. Your agent should now be live and ready to use.