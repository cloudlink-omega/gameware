# GameWare
A kind of ware to run your game.

## What is GameWare?

GameWare is a framework for building custom game servers on Omega. It allows your custom game logic to connect to lobbies and interact with players as if it were another player client, but with the reliability and capabilities of a server.

Omega provides a robust connectivity backend ("Signaling"). A key feature of Omega's Signaling is the **Relay Peer**. When a player creates a lobby with the "Enable Relay" feature, Omega's Signaling server manages this Relay Peer, and all broadcast messages within that lobby pass through it for efficient distribution to connected players.

GameWare provides an alternative and extended way to integrate server-side logic into this peer network. Instead of your game logic running directly on Omega's core Signaling server (like the Relay Peer), you can run an instance of GameWare independently on your infrastructure. This GameWare instance connects to the Omega Signaling server and participates in a lobby as a **"Game Peer"**.

From the perspective of the players in the lobby, the Game Peer appears and functions like any other player (though it's driven by your code). GameWare simplifies the process of connecting this independent peer and provides a structure for you to define **custom command handlers**. These handlers allow your server-side logic to listen for, process, and respond to specific messages within the lobby, vastly expanding upon basic broadcast messaging and enabling complex server-driven gameplay elements.

## Authentication

To connect and run a GameWare instance for your game, you will need specific credentials from your Omega Developer profile.

1.  **Set up Your Omega Developer Profile:** Ensure you have an active Developer profile on the Omega platform. (TODO: Link to Profile creation/login page)
2.  **Register Your Game:** You must have a game registered under your Developer profile. GameWare instances are tied to a specific registered game. (TODO: Link to Game Registration page)
3.  **Generate GameWare Credentials:** Within the Game Manager page for your registered game, you can generate a unique **GameWare Key** and **Secret**. These act as the credentials for your GameWare instance. (TODO: Link to Game Manager / Credential generation)

Your GameWare instance will require this **client key and secret** pair to successfully authenticate and connect to the Omega network. Please treat your secret key like a password and keep it secure on your server infrastructure.
