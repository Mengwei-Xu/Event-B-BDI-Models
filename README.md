# Event-B Models for BDI Agents in the CAN Language (with Pre-generated ProB Animation)

This repository contains all Event-B and ProB artefacts that are mentioned/used/developed in the following paper:


> *Algebraic Modelling and Proof-based Analysis of BDI Agents with Event-B*  
> Xu et al., submitted to JAIR

The artefacta consist of:

1. **Stack theory example** – a minimal Event-B theory illustrating polymorphic datatypes and operators, and their use in the Event-B formalism.
2. **BDI models** – Event-B projects containing the core BDI encoding and the robotic cleaning case study models, and its refined version for ProB animation. 
3. **Pre-generated animation (HTML)** – a browser-based animation of the robotic cleaning model, so users can inspect behaviour without installing Rodin or ProB.

All Event-B projects are provided as Rodin project archives (`*.zip`) or Eclipse-style project folders that can be imported directly into the Rodin Platform.

---

## Repository contents

```text
.
├── README.md                         # This file
├── LICENSE                           # License for this artefact
├── StackProject.zip                  # Stack theory example (Event-B project)
├── JAIR_Final_models.zip             # Final BDI encoding and case-study model (Event-B projects)
├── JAIR_Final_modelsProB.zip         # Finite-state and refined BDI encoding and case-study model (Event-B projects)
└── AnimationRobotCleaning.tar.gz     # Pre-generated HTML animation of the robotic cleaning model

```

## Quick start: view the HTML animation only

After extracting `AnimationRobotCleaning.tar.gz`, you should see:

```text

AnimationHTML/
├── BDISemanticsRoboticCleaning_mch.html
├── cleaningrobot.jpg
├── stone.png
└── waste.png
```

If you only want to see the behaviour of the robotic cleaning agent, you can skip Rodin installation steps below and just open the `BDISemanticsRoboticCleaning_mch.html` in any browser to view the animation. This animation also incorporates an SVG visualisation that are used for presenting the running example of the robotic cleaning scenario in the paper for extra friendliness. 


## Using the Event-B models (Rodin and ProB)

To inspect and run the Event-B models (not needed for just viewing the HTML animation), you need to do the following:

### 1. Install the Rodin Platform

Download the Rodin Platform from:

- <https://sourceforge.net/projects/rodin-b-sharp/>

Choose the distribution for your OS, unpack it, and follow the installation and usage instructions in the Rodin README or documentation.

---

### 2. Ensure the Event-B Theory plug-in is available

In Rodin:

1. Go to **Help → Install New Software…**.
2. In **Work with**, select the main Rodin update site  
   `http://rodin-b-sharp.sourceforge.net/updates`.
   (Different versions of Rodin may have different naming or multiple listings for this update site)
3. Under the category **Modelling Extensions**, select the **Theory** plug-in (or equivalent).
4. Complete the installation and restart Rodin.

For more details, see the Theory wiki page:  
<http://wiki.event-b.org/index.php/Theory_News_and_Support>

---

### 3. Install the ProB plug-in for Rodin

In Rodin:

1. Go to **Help → Install New Software…**.
2. In **Work with**, select the update site that provides **ProB** (this may be called “ProB for Rodin” or similar, depending on your distribution).
3. Select the **ProB** plug-in and install it.
4. Restart Rodin.

After restarting Rodin, you should see **ProB** entries in the context menu when you right-click on an Event-B machine or context (e.g. “Start Animation / Model Checking”). We note you cannot animate the model in `JAIR_Final_models.zip ` as they are not finite-state models (ProB will time out!). 

Howeverm you can animate the example in stack theory if you are interested in seeing how it works and ProB-version of the encoding. 
To do so, right click `StackM` file in `StackProject` folder, and select `Start Animation/Model Checking`. 
Again, you encounter any ProB animation issue, please reach to us as making ProB work can be tricky. 

---

### 4. Get this project into your Rodin workspace

> You do **not** need to unzip `StackProject.zip` or `JAIR_Final_models.zip`. Rodin can import these archives directly.

In Rodin, please go to **File** → **Open Projects from File System**, click **Archive**, then select, for example, `StackProject.zip` from this repository. The project will appear in the **Event-B Explorer**. You can then open the theory, context, and machine files as usual. 


### 5. Inspect proofs in Rodin

To inspect the proofs (especially the invariant safety properties for the running example) in Rodin, for example, first open the project `BDIAgentRobotCleaningModels` in the Event-B Explorer, expand the machine `BDISemantics` node, and then **Proof Obligations** view should now appear. This view lists all proof obligations (POs) generated from `BDISemantics`, including invariant preservation together with their status (proved, undischarged, pending). For example, green icons indicates a PO is proved. 

To inspect one in detail, double-click a PO to switch to the *Proving* perspective, where Rodin shows a proof tree and the applied rules. To enter the *Proving* perspective, please go to  **Window → Perspective → Open Perspective → Proving**. In the proving perspective, you can expand the proof tree to see how the invariant follows from the event’s guards, actions, and hypotheses, and you can replay the existing proofs. All proofs needed for e.g. the paper’s safety and faithfulness claims are already discharged; inspection is read-only unless you choose to change them.



## Reproducing the paper’s results

The artefacts support the following tasks:

1. Inspecting the formal encoding of the BDI/CAN language:
   * BeliefTheory and BDITheoryProject provide the underlying theories for encoding BDI syntax and semantics.

2. Checking faithfulness properties via Rodin proof obligations:
   * The structure of the encoding in data types and operators (totality, sort-disjointness, injectivity).
   * Semantic invariants and preservation proofs available in the **Proof Obligations** view in Rodin (displayed as proof trees).

3. Exploring the case study behaviour:
   * Via the pre-generated HTML animation in AnimationRobotCleaning.tar.gz (no toolchain required).
   * Via the model in the `JAIR_Final_modelsProB.zip`.


## License

The contents of this repository (models, HTML animation, and documentation) are made available under the MIT License. You are free to use, modify, and redistribute these artefacts, including in commercial and closed-source settings, provided that you include the copyright and license notice.


## Contact and issues

If you encounter problems importing, animating, or inspecting the models or the HTML animation, please open an issue in this repository or directly contact one of the following:

**Peter Rivière** – <priviere@jaist.ac.jp>  

**Mengwei Xu** – <Mengwei.Xu@newcastle.ac.uk>

