# Simply360

Status: prepared for directory review; the public listing is not yet available. Production deployment and live connection testing remain pending.

Connect your existing Simply360 account to Claude through the Simply360 MCP service. Once the listing is available, install the Simply360 plugin from Claude’s plugin directory, enable it, and sign in with Simply Login when prompted by the host’s OAuth flow. An existing Simply360 account is required; this package contains no credentials.

The plugin provides four read-only tools: `list_my_teams`, `list_data_collections`, `get_data_collection`, and `search_data_records`. Use them to find Teams you can access, browse their Collections, inspect readable field metadata, and search record names and summaries. Record searches use the SUMMARY projection and do not return field values or search custom fields.

Try prompts such as:

- “List the Simply360 Teams I can access.”
- “List the Collections in my selected Team and show their readable fields.”
- “Show me record names containing sample in [selected Collection].”

Results depend on your account permissions. The plugin does not create, edit, or delete records, and it does not expose generic execution, proposals, messaging, or payment tools. Report only results returned by Simply360 and follow the account’s permissions.

## Setup and troubleshooting

Once the hosted directory endpoint is deployed, you can test it by adding a custom connector in Claude’s Connectors settings with URL `https://api.simply360.app/v1/mcp/directory`. Sign in with Simply Login, complete your account’s MFA challenge, choose an authorized Team, and approve the requested read permissions. No API key is needed.

If sign-in does not finish, reconnect and complete the consent screen. If a Team or Collection is missing, check your Simply360 membership and read permissions. Empty search results may mean that no readable record name matches the search term. Revoke the connection under Simply360 User Account > Connected Apps.

The selected AI provider receives OAuth credentials and the requested tool results to operate the connection. Record names and summaries may contain personal information; connect only information you are authorized to share with the provider. See the privacy policy for Simply360’s retention and the provider’s own practices.

Website: https://simply360.app  
Support: https://simply360.app/contact  
Privacy: https://simply360.app/privacy-and-policy  
Terms: https://simply360.app/terms-of-use
