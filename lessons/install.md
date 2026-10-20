# Claude Desktop, Code tab

*In the workshop, the facilitator walks the room through this from the slides. This page is for doing it beforehand, or afterwards on your own.*

The Code tab is Claude with hands: it works inside a folder on your computer, reading and writing
the files there. The desktop app already includes Claude Code, so there is nothing else to install
(no Node.js, no command line). It needs a paid plan: Pro, Max, Team or Enterprise. Do this before
the day, and bring any error message with you.

## Do

1. Download Claude Desktop from **claude.com/download**, install it, and sign in.

   ![The claude.com/download page](../images/setup/install-claude-desktop.png)

2. Click the **Code** button (**</>**) at the top left. If it asks you to upgrade, your plan
   doesn't include it; tell the facilitator before the day.

   ![The Code button at the top left, next to Chat](../images/setup/code-tab.png)

3. Make an empty folder somewhere easy to find, for example `claude-test` in your Documents.
4. Click **+ New**. In the bar under the message box, choose **This computer**, then the folder
   button and **Open folder…**, and pick `claude-test`.

   ![The folder menu: recent folders, and Open folder](../images/setup/select-folder.png)

5. In the same bar, the mode button says **Auto**: that's the default. Click it and choose
   **Manual**. Leave **Bypass permissions** alone.

   ![The mode menu, with Auto ticked](../images/setup/select-mode.png)

6. **Predict:** you type *"Create a file called hello.txt that says hello"*. Will the file just
   appear? Will Claude ask you first? Where on your computer will it go?
7. Send it. Accept the change when it asks. Then open the folder in Finder or File Explorer and
   look.

## Proof

`hello.txt` exists in your test folder, and you opened it yourself.

## Misconceptions this exposes

- *"It's the same as the chat tab."* The Chat tab has no access to your files; the Code tab works
  in the folder you chose, and only there unless you allow more.
- *"I need to install developer tools first."* Not for this. Git comes next, and only because the
  later lessons use it.
