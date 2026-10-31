# Build Dependencies
## What You need to compile the base desktop enviroment.
### Dependency table definitions
| Dependency Table Column Name | Dependency table Column Name Definition | Dependency Table Column Name Acceptable Values | 
| -------------- | -------------- | -------------- |
| Dependency Name | Name of the Dependency project used by Unity | N/A |
| Classification | What the Dependency project does outside of Unity | N/A |
| Build Need Status | How critical is this dependency to unity during build? | Mandatory, Required, Optional, None |
| Required during use? | Is this dependency required while Unity is active? | Yes/No |
| Current Usage Status | Lifecycle of the dependency in relation to Unity | Active, Being Phased Out, Obsolete |
| Notes | Freeform area to note the usefulness of the dependency in relation to unity | N/A |
| Fork Required? | Do we need to inherit maintainership of this dependency? | Yes, No, Unsure |
| Fork Source if forked | Where did we get the source code to continue maintaining this dependency? | Link to the most trustworthy, Accurate source required by the base version archived in V0 |
| Fork Git hash | The full-length non-tree hash for the forked item | N/A |
| Fork Tree Hash | The full-length tree hash for the forked item | N/A |
| Bazaar Version Data (where applicable) | Contains the bazaar branch information and tree tag information for sources available through exclusively bazaar, or have their most trustworthy source available only on bazaar. | Bazaar upstream link + Revision + Revision commit number |
### Dependency Table
| Dependency Name | Classification | Build Need status | Required during use? | Current Usage Status | Notes | Fork Required? | Fork Source If forked | Fork Reason | Fork Git hash | Fork Tree Hash | Bazaar Version Data (where applicable) |
| -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- |
| Bazaar | Git-like Alternative | None | No | Obsolete | Historical Build dependency, Does not provide extra value. | No | N/A | N/A | N/A | N/A | N/A |
| Nux | GUI toolkit | Mandatory | Yes | Active | Core Component of Unity, Required for GUI Rendering | Yes | https://github.com/3v1n0/nux | Unmaintained Necessary Source, Rolled inward to preserve the look and feel of unity | 03274cb6cb98e62869d8d2d7ae4d3b5ceaa30e2d | 2acab3bfad2f7e9882b9768852684cf2dc669992 | N/A |
| Compiz | Tiling OpenGL based window manager | Mandatory | Yes | Active | Core Component of Unity, Handles window tiling, Animations and more | Yes | https://github.com/jaijeet/compiz | Unmaintained Necessary Source, Rolled inward to preserve the look and feel of unity |  606332e9f0465c3e5680ef8360a26ee172e9df3f | 9ed33ea310dd29f6496232b4a8ec6c3eef8b6545 | N/A |
| Dee | DBUS Extension providing a Shared Data Framework | Mandatory | Yes | Active | Core Component of Unity, Provides objects to aid Unity during operation | Yes | https://launchpad.net/dee | Rolled inward from bazaar, No modern trustworthy source with maitnance available. | N/A | N/A | https://code.launchpad.net/~unity-team/dee/trunk Revision 437 |
| BAMF | Application matching wrapped into a DBus daemon and C library | Mandatory | Yes | Active | Core Component of Unity, Responsible for search functionality components and app matching | Yes | https://launchpad.net/bamf | Active maintainership present, but attempting to compile Unity against the latest release does not seem very fesable. Forking a known good version was chosen instead. | 24ea43f2fa2457989ff430ffa21f4ca07ae60168 | 901a202df97f89fb3e9e544621f094ae5fb56b1a | N/A |
| libindicator | Provides conveinence functions and symbols for Indicators within the Atayana Project | Mandatory | Yes | Active | Core Component of Unity, Provides the the base library for top bar indicators. | Yes | https://launchpad.net/libindicator | Rolled inward from bazaar, Modern repository found but bazaar selected first due to proximity to Canonical-era Unity | N/A | N/A | https://code.launchpad.net/~indicator-applet-developers/libindicator/trunk.16.10 Revision 533 |
