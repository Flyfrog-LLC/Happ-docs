# Examples of links and parameters

### Parameters

<details>

<summary>allowInsecure</summary>

Allows connections without TLS certificate verification.\
Set in the configuration URL:

* For **VMess**:\
  `"allowInsecure": "1"`
* For other protocols:\
  `allowInsecure=1`

</details>

<details>

<summary>fragmentation</summary>

This enables traffic fragmentation. It can be configured globally (via app settings) or per server:

* **Global setting** — applies to all connections.
* **Per-server setting**:
  * **VMess**:\
    `"fragment": "1-10,5-20,tlshello"`
  * **Others**:\
    `fragment=3,1,tlshello`

</details>

<details>

<summary>title</summary>

Server name (up to 30 characters).\
If it exceeds the screen width, it will be truncated with ellipsis (`...`).\
Defined at the end of the config after `#`.

**Example:**\
`vmess://...#My_Server`

</details>

<details>

<summary>serverdescription</summary>

Available **only when `ProviderID` is set**.\
Displays a subtitle below the server name instead of protocol labels like "VMess", "VLESS", or "Trojan".

* Max length: 30 characters
* Truncated with `...` if too long
* Specified after the title with `?`

**Example:**\
`vmess://...#MyServer?serverdescription=Netflix`

</details>
