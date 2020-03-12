# Dactyl Manuform 4x5


Shopping list 1

- 3D printed model (PLA, blue)
  The model might need changes for the Kailh switches.
  https://www.craftcloud3d.com/
  29.25 GBP

- Switches (44 min): Kailh x Novelkey BOX Heavy Switch Burst Orange
  https://www.opticboards.com/product/switches/kailh-box-heavy
  and select "Burst Orange".
  16.50 GBP (50 switches)

- 2 Arduino Pro Micro with socket
  https://www.amazon.co.uk/dp/B07FQJW2KN/ref=twister_B07FW2H75W
  2 x 7.99 GBP

- Wires to connect controller
  https://www.amazon.co.uk/TeOhk-120pcs-Multicolored-Breadboard-arduino/dp/B07R7ND6MT/ref=sr_1_5
  4.99 GBP

- Enamelled wire / copper wire for columns
  https://www.amazon.co.uk/s?k=magnet+wire&ref=choice_dp_b
  https://www.amazon.co.uk/BNTECHGO-AWG-Magnet-Wire-Transformers/dp/B07DYF53ZN
  6.98 GBP

  OR

- Silicone wires for the columns
  Ex. https://www.amazon.co.uk/Anpro-Insulation-Wrapping-Colors-B-30-1000/dp/B07C4QPV4F
  8.99 GBP

- min 44 diodes
  https://www.amazon.co.uk/50-1N4148-Signal-Switching-Diode/dp/B00XWE2SYM/ref=zg_bs_10256463031_1

- Wire cutter
  https://www.amazon.co.uk/nuosen-Precision-Electrical-Cutting-Diagonal/dp/B07GCLHSTF

- Wire cutter/stripper if using silicone wires?
  https://www.amazon.co.uk/Electrical-Multifunctional-Automatic-Adjusting-Insulated/dp/B078134FXK/ref=zg_bs_1939061031_7
  https://www.amazon.co.uk/gp/bestsellers/diy/1939061031

- Left to Right cable (telephone cable)
  - 2 female RJ9 connectors
    - https://www.amazon.co.uk/WOVELOT-Female-Telephone-Connector-Adapter-Gray-Green-Red-Yellow-Black/dp/B07RQ5BHV5/ref=sr_1_66
    - https://www.aliexpress.com/item/32795349368.html
  - Telehone cable
    - https://www.aliexpress.com/item/32263908500.html
    - https://www.amazon.co.uk/Sourcingmap-Stretchy-Coiled-Telephone-Handset/dp/B07G29B6TD/ref=sr_1_4
    - https://www.amazon.co.uk/sourcingmap%C2%AE-Stretchy-Connector-Telephone-Handsets/dp/B00LUIQMH6/ref=pd_day0_hl_107_4/257-9634157-9212447
    - https://www.amazon.co.uk/SNANSHI-Telephone-Handset-Coiled-Spiral/dp/B015KO93VC/ref=sr_1_26
  
- DSA Keycaps orange
  https://www.aliexpress.com/item/32830177884.html
  12.63 GBP

## 3D Model

### Install clojure

Using asdf
```
asdf plugin-add clojure https://github.com/halcyon/asdf-clojure.git
asdf install clojure 1.10.1
asdf global clojure 1.10.1
clojure
```

### Install Leiningen

```
asdf plugin-add lein https://github.com/miorimmax/asdf-lein.git
asdf list-all lein
asdf global lein 2.9.1
```

### Install OpenSCAD

```
wget -qO - https://files.openscad.org/OBS-Repository-Key.pub | sudo apt-key add -

sudo bash -c 'echo "deb https://download.opensuse.org/repositories/home:/t-paul/xUbuntu_18.04/ ./" > /etc/apt/sources.list.d/openscad.list'

sudo apt update

sudo apt install openscad-nightly
```

### dactyl-manuform project

```
git clone https://github.com/abstracthat/dactyl-manuform.git
cd dactyl-manuform
```

Copy current "things"

```
cp -a things things-old
rm things/*
```

Follow instruction on https://github.com/abstracthat/dactyl-manuform in order to create the new files.




# Flashing using the default QMK firmware

git clone from the QMK repository

## Install dependencies + avrdude

```
sudo apt-get install avrdude
```

## Install ModemManager.service

```
sudo systemctl stop ModemManager.service
```

## Check that the pro micro is detected (not all USB cables work)

```
lsusb
```

## Flash as root

```
sudo make handwired/dactyl_manuform/4x5:frisoft:avrdude

# when requested, reset connecting GND and RST pins
```
