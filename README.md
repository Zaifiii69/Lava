# Cherry Lava Boat (Fabric, Minecraft 1.21.1)

Cherry boats and cherry chest boats float and row on lava exactly like water.
The boats don't burn, and riders get a short fire-resistance effect while over lava.
All other boat types behave as vanilla.

## How it works
- `BoatEntityMixin` redirects the boat's "is this fluid water?" checks
  (`checkBoatInWater`, `getUnderWaterLocation`, `getWaterLevelAbove`, `fall`)
  so lava counts as water, for cherry boats only.
- `EntityMixin` makes cherry boats fire immune, so lava doesn't damage or ignite them.
- A tick hook gives passengers Fire Resistance while the boat is over lava.

## Build
Requires JDK 21. From this folder, with Gradle 8.8+ installed:

    gradle wrapper --gradle-version 8.8
    ./gradlew build

The jar appears in `build/libs/cherry-lava-boat-1.0.0.jar`. Drop it in your
`mods` folder along with Fabric API for 1.21.1.

## Notes
Mixin targets use Yarn names for 1.21.1. If the game reports a mixin target
not found, check the method names against your Yarn mappings.
