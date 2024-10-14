# League of Legends Skins for Developer Repository

This repository aims to provide a centralized and easily accessible location for all in-game skins available for League of Legends. The purpose of this project is not to undermine the custom skin scene within League of Legends. Instead, we aim to provide a solution for players who have been unable to afford skins since the introduction of Vanguard. Previously, these players relied on tools like LolSkin or R3nzSkin, which are no longer viable.

Using custom skins does not confer any competitive advantage, as they are only visible to the player utilizing them. 

The creator of this repository believes that with the implementation of predatory practices in skin sales — exemplified by exclusive skins like the Faker skin, which cost as much as three months' wages in some regions — Riot has restricted access to certain content for a significant portion of its player base. 

> We hold that gaming culture should be inclusive and accessible, not just a privilege for those who can afford it.

## Repository Structure

The repository is organized as follows:

```
/
├── 1/  # Annie
│   ├── 0.fantome  # Default skin
│   ├── 1.fantome 
│   ├── 2.fantome
│   └── ...
├── 2/  # Olaf
│   ├── 0.fantome # Default skin
│   ├── 1.fantome
│   └── ...
└── README.md
```

> [!IMPORTANT]\
> You will probably notice that there are more .fantome files in each champion folder than the actual number of skins for that champion. This is because the files include both skins and chromas, which we currently cannot reliably differentiate from which skin the chromas is.

The reasons for this are:

1. Riot Games does not follow a consistent pattern in assigning IDs to skins and chromas.
2. The gap between skin IDs is not uniform and cannot be used to reliably identify chromas colors or from which skin they are.

For example:
- A champion might have a skin with ID 3 that has 6 chromas.
- Logically, the next skin ID should be 10 (3 + 6 + 1), but it might actually be 4.

To better understand the relationship between these files and the actual skins/chromas:

1. Refer to the `API Endpoints` section below to learn how to retrieve official skin names.
2. Use these endpoints to cross-reference the .fantome files with the official skin data.
3. Be aware that some .fantome files may represent chromas, even if they're numbered sequentially.

We are continuously working on improving the organization and identification of skins and chromas. Your patience and contributions to this effort are greatly appreciated.

Each champion folder is named with its key (matching the "key" attribute from the champion data), and skin files within are numbered from 0 to n, where n is the last skin for that champion.

## API Endpoints

To get champion and skin names, you can use the following Data Dragon API endpoints:

1. Champion Data (including keys):
   ```
   https://ddragon.leagueoflegends.com/cdn/<version>/data/en_US/champion.json
   ```
   Replace `<version>` with the current game version (e.g., "14.20.1").

2. Skin Names for a Specific Champion:
   ```
   https://ddragon.leagueoflegends.com/cdn/<version>/data/en_US/champion/<champion name>.json
   ```
   Replace `<version>` with the current game version and `<champion name>` with the champion's name (e.g., "Annie").

Note: There is currently no known endpoint to retrieve chroma names.

## How to Use

1. Identify the champion key you're interested in using the champion data endpoint.
2. Navigate to the corresponding folder in this repository (e.g., `/1/` for Annie).
3. Download the desired skin file (e.g., `1.fantome` for the first skin).
4. Use the skin data endpoint to find the corresponding skin name if needed.
5. Apply the skin using a compatible tool such as:
   - [Fantome](https://github.com/LeagueToolkit/fantome)
   - [CSLOL](https://github.com/LeagueToolkit/cslol-manager)

Follow the installation instructions provided with these tools to implement the skins successfully.

## Wanna contribute?

You can simply contribute by ⭐ starring this repository. 

But, if you want to go a little further, you can:

1. Fork this repository.
2. Add or update the Fantome files in the appropriate champion folder.
3. Ensure the file naming convention (using sequential numbers) is followed.
4. Submit a pull request with a clear description of your changes.

For more details, check our [CONTRIBUTING.md](CONTRIBUTING.md) file.

## Disclaimer

This project is not endorsed by Riot Games and does not reflect the views or opinions of Riot Games or any of its affiliates. League of Legends and all related properties are trademarks or registered trademarks of Riot Games, Inc.

The use of these assets for skin hack development may violate Riot Games' terms of service. Use at your own risk.

This repository is not affiliated with the moderators of r/LoLCustom.

## Security Considerations for Developers

> [!WARNING]\
> Developers utilizing this repository should be aware of potential risks associated with direct use of these files. To mitigate the risk of Riot Games identifying and potentially blacklisting specific file hashes, we strongly recommend implementing a tool or process to alter the .wad.client file hash before every injection. This practice can help prevent easy detection and blacklisting of the files provided here.

Consider developing or using a tool that:
1. Reads the .fantome files from this repository
2. Makes minor, non-functional alterations to the file content (e.g., adding benign metadata or comments)
3. Generates a new file with a different hash but identical functionality

By implementing such a system, you can help protect users of your development from potential bans or other consequences, should Riot Games decide to take action against the use of these specific file hashes. Remember, the goal is to preserve functionality while avoiding direct matches to the files in this public repository.

Please note that while this method may reduce the risk of detection via hash matching, it does not guarantee protection against all forms of detection or potential consequences of using custom skins. Always inform your users about the risks involved in using custom skins or any modifications to the game client.

## Donation

If you find this project helpful, consider supporting the maintainers:

- Pix: b2763e55-ac97-4963-83e9-d9827caed2de
- Ko-Fi: https://ko-fi.com/koobzaar
