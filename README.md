<p align="center">
  <a href="#build-framework">
   <img src="https://raw.githubusercontent.com/armbian/build/master/.github/armbian-logo.png" alt="Armbian logo" width="144">
  </a><br>
  <strong>Armbian OS</strong><br>
<br>
<a href=https://github.com/armbian/os/actions/workflows/complete-artifact-matrix-all.yml><img alt="GitHub Workflow Status" src="https://img.shields.io/github/actions/workflow/status/armbian/os/complete-artifact-matrix-all.yml?logo=githubactions&label=Artifacts&style=for-the-badge&branch=main"></a> <a href=https://github.com/armbian/os/actions/workflows/repository-update.yml><img alt="GitHub Workflow Status" src="https://img.shields.io/github/actions/workflow/status/armbian/os/repository-update.yml?logo=githubactions&label=Repository&style=for-the-badge&branch=main"></a> <a href=https://github.com/armbian/os/actions/workflows/full-distro-build-and-test.yml><img alt="GitHub Workflow Status" src="https://img.shields.io/github/actions/workflow/status/armbian/os/full-distro-build-and-test.yml?logo=githubactions&label=Deboostrap&style=for-the-badge&branch=main"></a> <a href=https://github.com/armbian/os#latest-smoke-tests-results><img alt="GitHub Workflow Status" src="https://img.shields.io/github/actions/workflow/status/armbian/os/smoke-tests.yml?logo=githubactions&label=Smoke%20tests&style=for-the-badge&branch=main"></a>
</p>


## What does this project do?

- Builds quarterly [stable](https://www.armbian.com/download/), daily [rolling](https://github.com/armbian/os/releases/latest) and weekly [community](https://github.com/armbian/community/releases/latest) Armbian OS images
- Keeps build framework [packages artifacts](https://github.com/orgs/armbian/packages) cache up to date to secure fast rebuild process
- Keeps stable [apt.armbian.com](https://apt.armbian.com) and nightly [beta.armbian.com](https://beta.armbian.com) packages repository up to date
- Keep synchronizing the selection of [3rd party](external) applications with Armbian repositories
- Reversion Firefox, Thunderbird and Chromium to higher (9) epoch version then its Snapd counterparts (1)
- Tests install of all packages added onto stable and testing Debian and Ubuntu releases
- Tests packages upgrade sucess on real hardware
- Tests build [supported and community supported desktops](https://github.com/armbian/os/actions/workflows/full-distro-build-and-test.yml)

## How to enable images?

Build lists are generated [automatic](https://github.com/armbian/os/blob/main/.github/workflows/recreate-matrix.yml#L59-L211C94) based on [support policy](https://docs.armbian.com/User-Guide_Board-Support-Rules/) and with help of [templates](userpatches/), .blacklist and .map files.

## How to add description to download pages?

Each kernel branch can have additional description which is stoed in [kernel-description.json](kernel-description.json) and automatically updated upon changes.

## When is this happening?

- Artifacts cache is updated every eight hours, starting at 0:00 AM UTC
- Repository update starts after artifacts cache update is done succesfully
- Smoke tests starts once per day at 5:30 AM UTC
- Nightly images are build once per day, at 2:00 AM UTC, or if [build config / template is changed](https://github.com/armbian/os/blob/main/userpatches/targets-release-nightly.yaml)
- Manually, when Armbian [release manager](https://github.com/orgs/armbian/teams/release-manager) executes a build action

## Latest smoke tests results:

- installs **kernels**, **device tree blob** and **headers**
- runs **network** (iperf) and **computing performance** tests (7z benchmark)
- store **armbianmonitor** logs

<!--START_SECTION:data-section-->
<table width="100%"><tr><td align="left"><a id=Board ID href=#Board ID><b>Board name</b></a></td><td align=center><b>Kernel version</b></td><td align=center><b>Support</b></td><td align=left><b>Logs</b></td><td align=right><b>Iperf</b></td><td align=right><b>7z -b</b></td><td align=right><b>Repo</b></td></tr><tr><td align="left"><a id=odroidc2 href=#odroidc2>Odroid C2</a></td><td align=center>6.6.54-current-rockchip</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/okaculuqep><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>860</td><td align=right>4523</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapim2ultra href=#bananapim2ultra>Banana Pi M2 Ultra</a></td><td align=center>6.6.44-current-sunxi</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/uwulodoces><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>778</td><td align=right>2715</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-edge2 href=#khadas-edge2>Khadas Edge2</a></td><td align=center>n/a</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-edge2 href=#khadas-edge2>Khadas Edge2</a></td><td align=center>n/a</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidm1 href=#odroidm1>Odroid M1</a></td><td align=center>6.6.54-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/buramikewe><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>890</td><td align=right>3524</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidxu4 href=#odroidxu4>Odroid XU4</a></td><td align=center>6.6.51-current-odroidxu4</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ozozaqaluk><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>780</td><td align=right>7644</td><td align=right>beta</td></tr><tr><td align="left"><a id=lime-a64 href=#lime-a64>A64 OLinuXino</a></td><td align=center>6.6.44-current-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/xubebawofa><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>2697</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim1 href=#khadas-vim1>Khadas VIM1</a></td><td align=center>6.6.54-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/uqonihujir><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>90</td><td align=right>3723</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim2 href=#khadas-vim2>Khadas VIM2</a></td><td align=center>6.6.54-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/yiqabohawi><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>860</td><td align=right>6189</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepi5 href=#orangepi5>Orange Pi 5</a></td><td align=center>n/a</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepi5 href=#orangepi5>Orange Pi 5</a></td><td align=center>n/a</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapim2pro href=#bananapim2pro>Banana Pi M2Pro</a></td><td align=center>6.6.54-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ehimunajel><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>848</td><td align=right>6192</td><td align=right>beta</td></tr><tr><td align="left"><a id=rockpi-e href=#rockpi-e>Rockpi E</a></td><td align=center>6.6.54-current-rockchip64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/alewelugoq><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>91</td><td align=right>3127</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidc4 href=#odroidc4>Odroid C4</a></td><td align=center>6.6.54-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/naqihewose><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>4934</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidn2 href=#odroidn2>Odroid N2</a></td><td align=center>6.6.54-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/pehotemoko><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>850</td><td align=right>8911</td><td align=right>beta</td></tr><tr><td align="left"><a id=lepotato href=#lepotato>Le potato</a></td><td align=center>6.6.54-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/fuxexugoyi><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>90</td><td align=right>3612</td><td align=right>beta</td></tr><tr><td align="left"><a id=cubietruck href=#cubietruck>Cubietruck</a></td><td align=center>6.6.44-current-sunxi</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/worirupuza><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>378</td><td align=right>1025</td><td align=right>beta</td></tr><tr><td align="left"><a id=udoo href=#udoo>Udoo</a></td><td align=center>6.6.54-current-imx6</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/zudociqato><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>390</td><td align=right>2248</td><td align=right>beta</td></tr><tr><td align="left"><a id=uefi-x86 href=#uefi-x86>UEFI x86</a></td><td align=center>6.6.54-current-x86</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/muxuvalizo><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>839</td><td align=right>5252</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapim5 href=#bananapim5>Banana Pi M5</a></td><td align=center>6.6.54-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/esoxisaleg><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>860</td><td align=right>5492</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim3 href=#khadas-vim3>Khadas VIM3</a></td><td align=center>6.6.54-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ecibebevas><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>850</td><td align=right>7185</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopi-r4s href=#nanopi-r4s>NanoPi R4S</a></td><td align=center>6.6.54-current-rockchip64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/rahucudiza><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>890</td><td align=right>6558</td><td align=right>beta</td></tr><tr><td align="left"><a id=pineh64 href=#pineh64>Pine H64</a></td><td align=center>6.6.44-current-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/vurezatapo><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>840</td><td align=right>4339</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim4 href=#khadas-vim4>Khadas VIM4</a></td><td align=center>5.15.137-legacy-meson-s4t7</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ripecolele><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>520</td><td align=right>11845</td><td align=right>beta</td></tr><tr><td align="left"><a id=bigtreetech-cb1 href=#bigtreetech-cb1>BigTreeTech CB1</a></td><td align=center>6.6.44-current-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/idacacaqum><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>89</td><td align=right>3086</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopi-r6s href=#nanopi-r6s>NanoPi R6S</a></td><td align=center>6.1.75-vendor-rk35xx</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/yeguzojoji><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>899</td><td align=right>16108</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopi-r6s href=#nanopi-r6s>NanoPi R6S</a></td><td align=center>6.11.2-current-rockchip-rk3588</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/galehodida><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>900</td><td align=right>16442</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim1s href=#khadas-vim1s>Khadas VIM1S</a></td><td align=center>5.15.137-legacy-meson-s4t7</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/cawabaxeha><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>89</td><td align=right>3906</td><td align=right>beta</td></tr><tr><td align="left"><a id=rpi4b href=#rpi4b>Raspberry Pi 4</a></td><td align=center>6.6.54-current-bcm2711</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/inowihosim><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>840</td><td align=right>4885</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapim7 href=#bananapim7>Banana Pi M7</a></td><td align=center>6.1.75-vendor-rk35xx</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/uzemeneney><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>877</td><td align=right>18817</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapim7 href=#bananapim7>Banana Pi M7</a></td><td align=center>6.1.75-vendor-rk35xx</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/uzemeneney><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>877</td><td align=right>18817</td><td align=right>beta</td></tr><tr><td align="left"><a id=rpi4b href=#rpi4b>Raspberry Pi 4</a></td><td align=center>6.6.54-current-bcm2711</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/asiwofitew><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>91</td><td align=right>1859</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizeroplus href=#orangepizeroplus>Orange Pi Zero Plus</a></td><td align=center>6.6.44-current-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/magisawixi><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>842</td><td align=right>2691</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapicm4io href=#bananapicm4io>Banana Pi CM4IO</a></td><td align=center>6.4.13-edge-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=#><img src=https://img.shields.io/static/v1?label=&message=N/A&color=white></a></td><td align=right>840</td><td align=right>7122</td><td align=right>beta</td></tr><tr><td align="left"><a id=clearfogpro href=#clearfogpro>Clearfog Pro</a></td><td align=center>6.6.54-current-mvebu</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/iwufujofuf><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>897</td><td align=right>2225</td><td align=right>beta</td></tr><tr><td align="left"><a id=rock-5b href=#rock-5b>Rock 5B</a></td><td align=center>6.1.75-vendor-rk35xx</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/sizolokumu><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>901</td><td align=right>16123</td><td align=right>beta</td></tr><tr><td align="left"><a id=rock-5b href=#rock-5b>Rock 5B</a></td><td align=center>6.11.2-current-rockchip-rk3588</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/xiragugago><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>900</td><td align=right>16430</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopim4v2 href=#nanopim4v2>NanoPi M4V2</a></td><td align=center>6.6.54-current-rockchip64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/itaxagodor><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>900</td><td align=right>6521</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepi5-plus href=#orangepi5-plus>Orange Pi 5 Plus</a></td><td align=center>6.1.75-vendor-rk35xx</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/olitizuwol><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>898</td><td align=right>16161</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepi5-plus href=#orangepi5-plus>Orange Pi 5 Plus</a></td><td align=center>6.11.2-current-rockchip-rk3588</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/mudosofaza><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>890</td><td align=right>16014</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopi-r6c href=#nanopi-r6c>NanoPi R6C</a></td><td align=center>6.1.75-vendor-rk35xx</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/sudugocoqa><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>900</td><td align=right>16615</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopi-r6c href=#nanopi-r6c>NanoPi R6C</a></td><td align=center>6.1.75-vendor-rk35xx</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/sudugocoqa><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>900</td><td align=right>16615</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopi-r6c href=#nanopi-r6c>NanoPi R6C</a></td><td align=center>6.1.75-vendor-rk35xx</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/sudugocoqa><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>900</td><td align=right>16615</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidxu4 href=#odroidxu4>Odroid XU4</a></td><td align=center>6.6.51-current-odroidxu4</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/uyeqoxocuj><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>882</td><td align=right>8045</td><td align=right>beta</td></tr></table>
<!--END_SECTION:data-section-->

## Would you like to join spare hardware to this automated testings?

All you need to do is:

- deploy any latest Armbian image to hardware
- provide IP address
- [contact us](https://www.armbian.com/contact/)

Device has to be always on and easily accesible for you to re-image in case of failed upgrade.

## Development

- [Pull request](https://github.com/armbian/build/pulls)
- [Weekly developers meetings](https://forum.armbian.com/events/)
- [Forums for developers](https://forum.armbian.com/forum/4-advanced-users-development/)

## Download prebuilt images

- [quarterly released **standard support** builds](https://www.armbian.com/download/?device_support=Standard%20support)
- [automatic released **rolling release** builds](https://github.com/armbian/os/releases/latest) (daily or when code changes)
- [weekly released **community maintained** builds](https://github.com/armbian/community/releases/latest)

## Support

- [Using Armbian](https://forum.armbian.com/forum/23-using-armbian/)

## Contact

- [Forums](https://forum.armbian.com) for Participate in Armbian
- IRC: `#armbian` on Libera.chat
- Discord: [https://discord.gg/armbian](https://discord.gg/armbian)
- Follow [@armbian](https://twitter.com/armbian) on X (formerly known as Twitter), [Fosstodon](https://fosstodon.org/@armbian) or [LinkedIn](https://www.linkedin.com/company/armbian).
- Bugs: [issues](https://github.com/armbian/build/issues) / [JIRA](https://armbian.atlassian.net/jira/dashboards/10000)
- Office hours: [Wednesday, 12 midday, 18 afternoon, CET](https://calendly.com/armbian/office-hours)
