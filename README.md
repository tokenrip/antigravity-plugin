# Tokenrip

Tokenrip keeps your documents, tables and tasks in workspaces you can come back to. Save a plan in one chat and pick it up in the next, share a workspace with teammates, and connect more than one assistant to the same work. Changes to files, tables and tasks record who made them and why, so whoever picks up the work next can see what happened.

With Tokenrip connected, you can ask your assistant to:
- Save documents, notes and plans to a workspace, and keep earlier versions when you want them.
- Keep tables, such as a lead list, a budget or an itinerary, and add or update rows.
- Track tasks: add them, see what's still open, start one, and mark it done.
- Pick up a workspace where you or another assistant left off, and see what changed since the last look.
- Read the notes and decisions you pin to a workspace before starting work.
- Search a workspace's files.
- Share a file by link, or add someone to a workspace as a viewer or editor.
- Propose an email, post or other step outside the workspace, and wait for your approval before doing it.

You sign in with your email and a six-digit code. Each app you connect gets its own access, which you can revoke from the Tokenrip dashboard at any time.

## What this plugin does

This plugin connects the Antigravity App and CLI to Tokenrip's MCP server at `https://api.tokenrip.com/mcp`. Once connected, the assistant can read and save work in your Tokenrip workspaces, report what it did, and ask in Tokenrip before steps that need you. A request it leaves there waits until you decide.

The plugin holds the server's address and one skill, `tokenrip`, which tells the assistant when to reach for your Tokenrip workspaces and how to work in them: load a workspace before changing it, give each change a one-sentence reason, and ask you in Tokenrip before a step outside it. No key, no script.

## Install from a local copy

- **Antigravity App.** Copy the plugin folder to `~/.gemini/config/plugins/tokenrip` and restart the App. Open **Customizations → Installed → Tokenrip → Accounts → Sign in**.
- **Antigravity CLI.** Run `agy plugin install /path/to/tokenrip` with the path to the plugin folder. Run `agy plugin list` to see the installed plugin. In the interactive CLI, open `/plugin`, expand Tokenrip under **Installed**, and choose **Sign in**.

Complete Tokenrip sign-in in your browser and approve the connection. Copy the code from the Antigravity callback immediately after that approval into the waiting Tokenrip authorization prompt in the App or CLI.

## Try a prompt

- What workspaces do I have in Tokenrip?
- What's left on the task list in our renovation workspace?
- Pick up where my other agent left off on the launch plan.

## Your data

- **What Tokenrip keeps:** your account, and what you and your agents put in: files, tables, tasks, folders and workspaces, with the history of what changed in each.
- **The reason for a change:** with a change, an agent may send a short reason, which is kept with the change in the workspace history. That history is kept for as long as it's needed, then deleted, and it goes with its workspace.
- **Agent requests:** what each request sent and got back is kept for 30 days, so problems can be found and fixed. Secrets are removed first, and the contents of files, tables and connection calls are never kept, only their size. The rest of the record (which agent, which operation, when, the result and the reason) is kept for one year, or until the account is deleted.
- **Conversation IDs:** when an agent sends a conversation ID, only a one-way hash of it is kept.
- **No sale, no ads, no training:** Tokenrip doesn't sell data, doesn't show ads, and doesn't use your content to train AI models.
- **Deleting:** deleted files, folders, workspaces and bundles stay in the trash for 30 days and can be restored; other deletions are permanent. To delete your account, go to Settings in the Tokenrip dashboard.

The privacy policy is the full statement: https://tokenrip.com/privacy

## Disconnecting

Uninstalling the plugin does not revoke Tokenrip's access. To revoke it, sign in to your Tokenrip dashboard and revoke the Antigravity connection on the Agents page. The App and CLI in one profile share that connection.

## Links

- [Tokenrip setup guide](https://tokenrip.com/setup)
- [Connecting over MCP](https://docs.tokenrip.com/getting-started/mcp-server)
- [MCP tool reference](https://tokenrip.com/mcp)

## License

MIT. See [LICENSE](LICENSE).
