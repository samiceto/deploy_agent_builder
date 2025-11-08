  Part 1: Get Your Agent Builder Workflow ID

   1. Create and Publish Your Agent:
       * Go to Agent Builder (https://agentbuilder.google.com/) and create a new project.
       * Once your agent is ready, Publish and Deploy it.

   2. Copy Your Workflow ID:
       * In your deployed agent, go to the </> Code section.
       * Copy the Workflow ID. You will need this for your .env file.

  ---

  Part 2: Set Up Your Local Project

   1. Download the Sample App:
       * In Agent Builder, find and click on "Clone sample app" (usually in the bottom right).
       * Download the project as a ZIP file.

   2. Prepare the Project Folder:
       * Extract the ZIP file.
       * Rename the extracted folder to whatever you like (e.g., my-chat-app).
       * Open this folder in your code editor.

   3. Configure Environment Variables:
       * In the root of your project folder, create a new file named .env.
       * Add your credentials to this file like so:

   1         WORKFLOW_ID=your_workflow_id_here
   2         OPENAI_API_KEY=your_openai_api_key_here

  ---

  Part 3: Customize Your Chat Theme

   1. Design Your Theme:
       * Go to the ChatKit Studio Playground (https://chatkit.studio/playground).
       * Design the chat interface to your liking.

   2. Apply the Theme to Your Project:
       * Click the </> icon in the playground to view the code and copy the theme object.
       * In your code editor, open the file at src/components/ChatKitPanal.tsx.
       * Paste the copied theme code into the theme prop of the <ChatKitPanel> component.

   3. Test It Locally:
       * Open a terminal in your project folder and run:
   1         npm run dev
       * Your custom-themed chat app will now be running locally.

  ---

  Part 4: Deploy Your App to Vercel

   1. Install and Log In to Vercel:
       * Install the Vercel CLI globally:
   1         npm install -g vercel
       * Log in to your Vercel account (this will open a browser window):
   1         vercel login

   2. Deploy the Project:
       * In your terminal, run the command:
   1         vercel
       * Answer the deployment questions as follows:
           * Set up and deploy? → Y
           * Which scope? → Select your username
           * Link to existing project? → N
           * What's your project's name? → Enter a name (e.g., chatkit-app)
           * In which directory is your code? → . (just press Enter)
           * Want to modify these settings? → N

  ---

  Part 5: Final Configuration

   1. Set Environment Variables on Vercel:
       * Go to your project's settings on the Vercel dashboard.
       * Find the Environment Variables section.
       * Add your WORKFLOW_ID and OPENAI_API_KEY again here.
       * Redeploy your project for the new variables to take effect.

   2. Allowlist Your Domain in OpenAI:
       * Copy your Vercel project's URL.
       * Go to your OpenAI Domain Allowlist settings
         (https://platform.openai.com/settings/organization/security/domain-allowlist).
       * Add your Vercel domain.

  You're all set! Your agent is now live on the web.