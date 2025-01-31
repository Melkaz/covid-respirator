MakAir — Covid-19 Respirator
=====

**Mass-producible open-source Covid-19 ARDS respirator. Aims at helping hospitals cope with a possible shortage of professional respirators during the outbreak. Worldwide.**

We are a distributed team of 200+ contributors, mostly spread through France. Makers, developers, university teachers, researchers and medical teams collaborated on this project. Our testing & assembly operations are located in France.

As to ensure international outreach, we made sure that contents required to build your own MakAir respirator are available in English.

If you're new there, please read the explanations below. _Your contributions are much welcome!_

![MakAir Logo](./res/assets/logo-readme.png)

---

➡️ **Update (6th April 2020):** We are ongoing finalization, endurance testing and final industrialization of our V1 MakAir respirator design. In the meantime, clinical trials have been started. We will provide more information (very) soon.

---

**Shortcut links:**

* [General EN/FR docs on Google Docs](https://docs.google.com/document/d/1l1nt0o93kdfcmPygp1k6NYKrwIb_uN01kcBAfovy2dE/edit)
* [Regular video updates on YouTube](https://www.youtube.com/channel/UCcf_3KXjeJSMz39J6gsyTSg)

---

# Abstract

Roughly, the idea is as follows: as of April 2020 and due to the Covid-19 pandemic, hospitals will soon start lacking mechanical artificial respirators. We built a pump, and a valve system (controlled by electronics). This way, the breathing cycle can be enforced by proper air routing through the valve system.

Our respirator is able to handle pressure-controlled breathing, stabilized using a [PID controller](https://en.wikipedia.org/wiki/PID_controller) in the software.

In order to ensure a proper breathing cycle (inhale + exhale), multiple valves need to be connected together to form a circuit. The motors needs to be controlled in harmony so that the air routing between each valve unit is consistent.

This project provides all the parts required to build a good-enough [ARDS](https://en.wikipedia.org/wiki/Acute_respiratory_distress_syndrome) respirator from mass-produced components. We provide all the required mechanical parts, electronics designs & boards, and firmwares. This respirator can be 3D-printed and ran on an Arduino board (the maker way), though we **highly advise** that you work with industrial processes as to mold medical-grade plastic parts and assemble the whole respirator (this would be required for the built respirator to pass all medical certifications).

We target a per-unit cost well under 500 EUR, which could easily be shrunk down to 200 EUR or even 100 EUR per respirator given proper economies of scale, as well as choices of cheaper on-the-shelf components (eg. servomotors).

Mechanically-speaking, the overall system is composed of sub-components that can be plugged together and wired to form an air circuit, namely:

- **Air pump** (called "Blower");
- **Air pump casing fit** (called "Blower Holder");
- **Valve system** (called "Pressure Valve");
- **Oxygen Mixer valve** (called "Oxygen Mixer");
- **Air filter casing (patient variant)** (called "Patient Filter Box");
- **Air filter casing (machine variant)** (called "Machine Filter Box"; intake + outtake);
- **Connectors** (called "Pneumatic Connectors");

All those components are fitted in box (ie. a container) that we designed:

- **Housing container** (called "Container");

# Warning Notices

**⚠️ A few important words before you start:**

1. Though 3D-printing (FDM and SLA) can be used to build your own respirator — this will definitely not scale well to mass-produce MakAir respirators, and parts might be brittle or leak air. Please work with proper industrial methods and processes if you want to build your own MakAir respirators.

2. As ARDS patients are sedated, their breathing cycle is forced by mechanical ventilation, while they are intubated. A failing respirator (due to bad mechanics, pneumatics or software) could kill the patient, or permanently damage their lung alveoli. It is critical that any self-built MakAir respirator is tested against a lung simulator system (eg. [ASL 5000](https://www.ingmarmed.com/product/asl-5000-breathing-simulator/)), and validated by medical experts.

3. Medical-grade plastic should be used to produce ventilators, and any kind of grease or adhesive chemicals must be avoided in the respirator. The ventilators should be produced in a [cleanroom](https://en.wikipedia.org/wiki/Cleanroom) as to avoid dust & germ contaminations.

4. The pneumatic circuit should be thoroughly tested for leaks and its ability to withstand elevated positive air pressure. Joints should be used where relevant, and medical-grade flexible pipes should be used between components.

5. While the MakAir respirators produced on-site in France were validated by a medical & engineering board, you should independantly seek validation of the MakAir respirators that you produce; as your assembly methods or parts may vary with ours.

_MakAir and Makers For Life should not be held resposible — at any time, for harm caused to human life (eg. lung damage or loss of life). By building your own MakAir, you are held responsible for its safety validations & use._

# How To Build?

🚧 (work in progress)

# Components

## Mechanics

| Part | Version | Last Changelog | Ready? | Live CAD Models | Contributors |
| ---- | ------- | -------------- | ------ | --------------- | ------------ |
| [Blower](./src/mechanics/parts/blower) | V14 | Smaller form factor & more powerful | ❌ | [view model](https://a360.co/39JpHg9) | Gabriel Moneyron + [Baptiste Jamin](https://github.com/baptistejamin) + [Valerian Saliou](https://github.com/valeriansaliou)
| [Blower Holder](./src/mechanics/parts/blower-holder) | V1 | Initial version | ✅ | [view core model](https://a360.co/2X7eoLW) + [view casing model](https://a360.co/2X5DwCR) | Gabriel Moneyron + [Valerian Saliou](https://github.com/valeriansaliou)
| [Pressure Valve](./src/mechanics/parts/pressure-valve) | V6 | General improvements | ✅ | [view model](https://a360.co/2xUBD1e) | [Clement Niclot](https://github.com/clementniclot)
| [Oxygen Mixer](./src/mechanics/parts/oxygen-mixer) | V5 | New compact design with integration plate | ✅ | [view model](https://a360.co/2Rgpefc) | [Yohann Nédélec](https://github.com/Melkaz) & Steven Daix
| [Patient Filter Box](./src/mechanics/parts/patient-filter-box) | V6 | Update input/output mensurations | ✅ | [view model](https://a360.co/2X5VvJq) | Martial Medjber + [Eliott Vincent](https://github.com/eliottvincent)
| [Machine Filter Box (Intake)](./src/mechanics/parts/machine-filter-box) | V1 | Wall-mountable, 3D-printability optimizations | ✅ | [view model](https://a360.co/2wZids4) | [Valerian Saliou](https://github.com/valeriansaliou)
| [Machine Filter Box (Outtake)](./src/mechanics/parts/machine-filter-box) | V1 | Wall-mountable, 3D-printability optimizations | ✅ | [view model](https://a360.co/2JyLaxG) | [Valerian Saliou](https://github.com/valeriansaliou)
| [Pneumatic Connectors](./src/mechanics/parts/pneumatic-connectors) | V2 | Updated version | ✅ | none | Gabriel Moneyron
| [Container](./src/mechanics/container) | V2 | Update mensurations | ❌ | [view model](https://a360.co/3dVmJbR) | Arthur Dagard

## Electronics

| Board | Version | Major Changes | Ready? | Contributors |
| ----- | ------- | ------------- | ------ | ------------ |
| [Motherboard](./src/electronics/motherboard) | V1.1 | Working PCB w/ software | ✅ | [Tronico (company)](https://www.tronico-alcen.com/) + Cherine Kamel + [Pierre Papin](https://github.com/pi-r-p)

## Software

| Runtime | Version | Major Changes | Ready? | Contributors |
| ------- | ------- | ------------- | ------ | ------------ |
| [Respiratory Firmware](./src/software/firmware) | V1.1.x | Initial test working | ✅ | [Emmanuel Feller](https://github.com/Mefl) + [Gautier de Saint Martin Lacaze](https://github.com/jabby) + [David Sferruzza](https://github.com/dsferruzza) + [Baptiste Jamin](https://github.com/baptistejamin) + Gabriel Moneyron
| [Control Unit](./src/software/control) | V0.1.x | Project started | ❌ | [Valerian Saliou](https://github.com/valeriansaliou) + [Quentin Adam](https://github.com/waxzce)

# Schemes

## Pneumatic Circuit Scheme

[![Pneumatic Circuit Scheme](./docs/Pneumatics/Pneumatic%20Circuit/Pneumatic%20Circuit.png)](./docs/Pneumatics/Pneumatic%20Circuit/Pneumatic%20Circuit.png)

_(design by [Valerian Saliou](https://github.com/valeriansaliou))_

## Container Layout

### Top Part: Electronics (Power & Controllers)

[![Container Layout Electronics Drawing](./docs/Container/Container%20Layout/Container%20Layout%20Electronics.jpg)](./docs/Container/Container%20Layout/Container%20Layout%20Electronics.jpg)

_(design by Arthur Dagard; drawing by [Valerian Saliou](https://github.com/valeriansaliou))_

### Bottom Part: Pneumatics

[![Container Layout Pneumatics Drawing](./docs/Container/Container%20Layout/Container%20Layout%20Pneumatics.jpg)](./docs/Container/Container%20Layout/Container%20Layout%20Pneumatics.jpg)

_(design by Arthur Dagard; drawing by [Valerian Saliou](https://github.com/valeriansaliou))_

# News & Contact

## Updates

* Live updates on Telegram: [join "Newsroom Covid-19 Respirator"](https://t.me/joinchat/AAAAAE_99-k7pKZur-GXCQ)
* Coordination on Slack: [request to join "Makers For Life"](https://github.com/covid-response-projects/covid-respirator/issues/new) (open an issue)

## Contacts

* Open-source & questions: [please open an issue on GitHub](https://github.com/covid-response-projects/covid-respirator/issues/new)
* Press contacts: Grégory Thibord
* Medical contacts: Pierre Antoine Gourraud
* Industry relations: [Quentin Adam](http://waxzce.org/)
* Engineering contacts: [Valerian Saliou](https://valeriansaliou.name/), [Eliott Vincent](https://eliottvincent.com/)

# Sponsors & Contributors

This project would not have been possible without the support of those companies and organizations, which have put human, real estate and/or financial resources at work on the project:

* [Clever Cloud](https://www.clever-cloud.com/) (founding team)
* [Crisp](https://crisp.chat/) (founding team)
* [Cooprint](https://cooprint.fr/) (CAD)
* [Tronico](https://www.tronico-alcen.com/) (PCB design)
* [Le Palace Nantes](https://lepalace.work/)

Adding to that, 200+ individual members of the project who contributed to technical, legal, medical and press subjects (and more).

# Renders

## Mechanics

### The "Pressure Valve"

<p>
  <img alt="Pressure Valve Render" src="./src/mechanics/parts/pressure-valve/fdm/schemes/V6/Pressure%20Valve%20(Render%201).png" height="240">
  <img alt="Pressure Valve Print" src="./src/mechanics/parts/pressure-valve/fdm/schemes/V6/Pressure%20Valve%20(Print%201).jpg" height="240">
</p>

### The "Blower"

🎦 View: [Animation of the "Blower"](./src/mechanics/parts/blower/fdm/schemes/V14/Blower%20(Animation%201).mp4)

<p>
  <img alt="Blower Render" src="./src/mechanics/parts/blower/fdm/schemes/V14/Blower%20(Render%201).png" height="240">
  <img alt="Blower Render" src="./src/mechanics/parts/blower/fdm/schemes/V14/Blower%20(Render%202).png" height="240">
  <img alt="Blower Render" src="./src/mechanics/parts/blower/fdm/schemes/V14/Blower%20(Print%201).jpg" height="240">
  <img alt="Blower Render" src="./src/mechanics/parts/blower/fdm/schemes/V14/Blower%20(Print%202).jpg" height="240">
</p>

### The "Blower Holder"

<p>
  <img alt="Blower Holder Render" src="./src/mechanics/parts/blower-holder/fdm/schemes/V1/Blower%20Holder%20(Render%201).png" height="240">
  <img alt="Blower Holder Print" src="./src/mechanics/parts/blower-holder/fdm/schemes/V1/Blower%20Holder%20(Print%201).jpg" height="240">
</p>

### The "Oxygen Mixer"

<p>
  <img alt="Oxygen Mixer Render" src="./src/mechanics/parts/oxygen-mixer/fdm/schemes/V4/Oxygen%20Mixer%20(Render%201).png" height="240">
  <img alt="Oxygen Mixer Print" src="./src/mechanics/parts/oxygen-mixer/fdm/schemes/V4/Oxygen%20Mixer%20(Print%201).jpg" height="240">
</p>

### The "Machine Filter Box" (Both Directions)

<p>
  <img alt="Machine Filter Box Render" src="./src/mechanics/parts/machine-filter-box/fdm/schemes/V1/Filter%20Box%20(Render%201).png" height="320">
  <img alt="Machine Filter Box Print" src="./src/mechanics/parts/machine-filter-box/fdm/schemes/V1/Filter%20Box%20(Print%201).jpg" height="320">
</p>

### The "Patient Filter Box"

<p>
  <img alt="Patient Filter Box Render" src="./src/mechanics/parts/patient-filter-box/fdm/schemes/V6/Filter%20Box%20(Mensurations).JPG" height="320">
  <img alt="Machine Filter Box Print" src="./src/mechanics/parts/patient-filter-box/fdm/schemes/Archives/V5/Filter%20Box%20(Print%201).jpg" height="320">
</p>

### The "Pneumatic Connectors"

<p>
  <img alt="Pneumatic Connector Blower Render" src="./src/mechanics/parts/pneumatic-connectors/fdm/schemes/V2/Blower%20V5/Pneumatic%20Connector%20Blower%20V5.png" height="240">
  <img alt="Pneumatic Connector O2 Render" src="./src/mechanics/parts/pneumatic-connectors/fdm/schemes/V2/O2%20V3/Pneumatic%20Connector%20O2%20V3.png" height="240">
  <img alt="Pneumatic Connector No pressure Render" src="./src/mechanics/parts/pneumatic-connectors/fdm/schemes/V2/Respiratory%20-%20No%20pressure/Pneumatic%20Connector%20Respiratory%20No%20pressure.png" height="240">
  <img alt="Pneumatic Connector pressure Render" src="./src/mechanics/parts/pneumatic-connectors/fdm/schemes/V2/Respiratory%20-%20Pressure%20V2/Pneumatic%20Connector%20Respiratory%20Pressure%20V2.png" height="240">
  <img alt="Pneumatic Connector O2 Print" src="./src/mechanics/parts/pneumatic-connectors/fdm/schemes/V2/O2%20V3/Pneumatic%20Connector%20O2%20V3%20Print.jpg" height="240">
  <img alt="Pneumatic Connector Blower Print" src="./src/mechanics/parts/pneumatic-connectors/fdm/schemes/V2/Blower%20V5/Pneumatic%20Connector%20Blower%20V4%20Print.jpg" height="240">
  <img alt="Pneumatic Connector No pressure Print" src="./src/mechanics/parts/pneumatic-connectors/fdm/schemes/V2/Respiratory%20-%20No%20pressure/Pneumatic%20Connector%20Respiratory%20No%20pressure%20Print.jpg" height="240">
</p>

### The "Container"

<p>
  <img alt="Container Render" src="./src/mechanics/container/molding/schemes/V2/Container%20(Render%201).png" height="240">
  <img alt="Container Render" src="./src/mechanics/container/molding/schemes/V2/Container%20(Render%202).png" height="240">
  <img alt="Container Render" src="./src/mechanics/container/molding/schemes/V2/Container%20(Render%204).png" height="240">
  <img alt="Container Render" src="./src/mechanics/container/molding/schemes/V2/Container%20(Render%206).png" height="240">
  <img alt="Container Render" src="./src/mechanics/container/molding/schemes/V2/Container%20(Render%207).png" height="240">
  <img alt="Container Render" src="./src/mechanics/container/molding/schemes/V2/Container%20(Render%208).png" height="240">
  <img alt="Container Assembly" src="./src/mechanics/container/molding/schemes/V2/Container%20(Assembly%201).jpg" height="240">
</p>

## Electronics

### The "Motherboard"

<p>
  <img alt="Motherboard Picture" src="./src/electronics/motherboard/schemes/V1/Motherboard%20(Picture%201).jpg" height="240">
  <img alt="Motherboard Picture" src="./src/electronics/motherboard/schemes/V1/Motherboard%20(Picture%202).jpg" height="240">
</p>
