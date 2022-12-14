# palera1n-guide

**ALERT!** This guide **may be invalid** if palera1n changes.

### Linux
On Linux **always** run palera1n with `sudo` (e.g. `sudo ./palera1n.sh --tweaks 15.0.2`).

## Dry run (try palera1n without installing Pogo)
1. Open Terminal and paste `git clone --depth 1 -b tweaks --recursive https://github.com/palera1n/palera1n && cd palera1n`.
2. Put your iDevice in DFU mode.
3. In the same Terminal window paste based on your needs:
   * for **tweaks**: `./palera1n.sh --tweaks 15.0.2 --no-install`
   * for **rootless**: `./palera1n.sh --dfu 15.0.2 --no-install`
4. Follow instructions on the screen.
5. After booting completed unplug iDevice from PC.
6. Test your iDevice for at least 1 hour.
   * Usefull tests are download apps from AppStore, lock screen (for deepsleep bug), WiFi connections, etc...
7. In the same Terminal window run `./palera1n.sh clean && rm -rfv blobs`.
8. Go to <a href="#item2">step 2 of "To install Pogo for the first time"</a> if **ONLY previous test passed**.
9. If tests failed for both **tweaks** and **rootless**, sorry for now you can't JB. You must **reboot** your iDevice to return in normal mode.

## To install Pogo for the **first time**
<ol>
    <li id="item1">Open Terminal and paste <code>git clone --depth 1 -b tweaks --recursive https://github.com/palera1n/palera1n && cd palera1n</code>.</li>
    <li id="item2">Replace <code>ramdisk/sshrd.sh</code> with my <code><a href="https://raw.githubusercontent.com/lorenzoferron98/palera1n-guide/main/sshrd.sh">sshrd.sh</a></code>.</li>
    <li id="item3">In the same Terminal window paste <code>chmod +x ramdisk/sshrd.sh</code>.</li>
    <li id="item11">Plug iDevice to your PC.</li>
    <li id="item4">Put your iDevice in DFU mode.</li>
    <li id="item5">In the same Terminal window follow the "number" based on your needs:</li>
      <ul>
        <li>for <b>tweaks</b>:  paste <code>./palera1n.sh --tweaks 15.0.2</code> I suppose the build number is 19A404.</li>
        <li>for <b>rootless</b>: paste <code>./palera1n.sh --dfu 15.0.2</code> I suppose the build number is 19A404. </li>
      </ul>
    <li id="item6">Follow instructions on the screen.</li>
    <li id="item7">After booting completed open Tips now Pogo.</li>
    <li id="item8">Tap Install button.</li>
    <li id="item9">Close Tips/Pogo app and open Sileo.</li>
    <li id="item10">Enjoy!</li>
</ol>

## To update folder `palera1n`
1. Open Terminal inside `palera1n`.
2. Run `git reset --hard && git pull`.
3. Run `./palera1n.sh clean`.
4. Go to <a href="#item2">step 2 of "To install Pogo for the first time"</a>.

## To only power on your iDevice in jailbroken state
1. Open Terminal inside palera1n
2. Put iDevice in DFU mode.
3. Run `./palera1n.sh --dfu 15.0.2 --no-install` to only boot your iDevice. Remember Pogo and Sileo are already installed.

## To restore RootFS and so to **remove palera1n** and **ALL YOUR DATA**
1. On your iDevice open Settings.
2. Go to General > Transfer or Reset iPhone > Erase All Content and Settings > Continue
3. Wait iDevice reboots in Setup.app.
4. After completing setup. Go to <a href="#item4">step 4 of "To install Pogo for the first time"</a>.
