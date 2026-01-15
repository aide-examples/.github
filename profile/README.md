<img src="AIDE.jpg" align="left" style="margin-right:20px;width:200px;"/> **AIDE Examples** demonstrate how to build professional software using agent-based development.

We provide well-engineered practical examples for educational purposes - be it in classroom or for self-study.

All projects were built in co-operation with AI agents (mainly *Anthropic Claude Console*).
Less than 2% of source code and documentation were manually crafted.

---

If you want to contribute more AIDE Examples, contact the author personally.

---

 # 📚 AIDE - Artificial Intelligence for Development Engineers

Agents can operate on par with experienced human software developers and contribute to impressive productivity gains. However, without stringent guidance, they quickly produce redundant, inconsistent, and poorly structured code mountains that no human wants to read anymore. And - even more importantly - humans can no longer take responsibility for the correct functioning of such systems.

But there is a different way.

AIDE proves that *it depends on us humans what comes out*. We can develop medium-sized systems with professional software architecture in collaboration with AI agents.

To do this, in addition to describing our functional requirements, we must employ numerous templates and architecture prompts that guide the agent's behavior so that it acts like a member of a professional development team.

The key to success is to *establish and maintain cooperation between human and agent on multiple levels (Design, Planning, Coding, Test)*, without leaving the agent's potential untapped through overly tight control. We call this concept [Human Periodically in the Loop](#human-periodically-in-the-loop)".

---

## AIDE - Application Systems

We plan to develop several *medium size systems* for different domains, from games to business information systems and social systems to technical applications (embedded systems). We also provide some *didactic material* based on small tasks, leading from zero to a well engineered script or a tiny system.

The systems are intended to serve as demonstration objects in in-house training and at universities. They should be useful as starting points for further development or reengineering steps.

### [AIDE - Quiz](https://github.com/aide-examples/aide-quiz) (medium size application)
The first AIDE application is an online quiz game with a relatively simple architecture, consisting of a web UI and server components with a database. It currently comprises approximately 20,000 lines (code and documentation). This makes it complex enough to demonstrate certain principles of good design. At the same time, the application domain is so simple that it can be understood in a few minutes.

### [AIDE - Frame](https://github.com/aide-examples/aide-frame) (small framework)
A lightweight application framework with server-side (Python) and client-side (JS/CSS) components, especially suited for Raspberry Pi deployments.
Originally it was part of aide-slideshow and was extracted from there. It is planned to provide a js server side implementation sonewhen in future. 
Main featires are logging, config handling, remote update mechanism, internationalization, markdown viewer.

### [AIDE - Frame Demo (Python)](https://github.com/aide-examples/aide-frame.demo-py) (small framework)
A simple python program which demonstrates how to use the aide-frame components. Could be used as a starting point for your own project.

### [AIDE - Slideshow](https://github.com/aide-examples/aide-slideshow) (small system)
This is a technical system running on a tiny raspberry (rpi zero 2WH) attached to a wall mounted screen. It can be controlled via a classical infrared control and via a web UI. It detects motion, ambient light and screen orientation. Images can be uploaded and prepared to match screen dimensions, add frames etc. We discussed with the AI how to keep the memory footprint of the system small enough to fit on that tiny device. The application also runs in the development environment where sensor hardware is replaced by stubs. Issues like remote software update, watchdog and protecting the systems against SD-card damage by sudden power loss are discussed.

### [AIDE - Knight](https://github.com/aide-examples/aide-knight) (didactic material)
This is a paper describing how teaching the fundamentals of programming might benefit from Agentic Coding.
The well-known chess knight's tour problem is often used to explain the concept of recursion. What can we gain and what will we lose if we delegate some work to an AI agent? The paper describes the teaching process and presents some illustrative material line AI promts, AI responses, scripts produced and finally an animated graph produced by the latest iteration of the script.

### AIDE Shelly (not available yet)
*Shelly* is a brand of the Bulgarian company *Allterco Robotics*, which specializes in the development of smart home solutions. Some devices use ESP32 processors and can be programmed via a web UI. There is a good API documentation available and the installed number of devices is pretty large. As they are also quite cheap we think taht they are ideal for teaching some apects of embedded systems design (though by far not all of them). We will show how to create scripts which allow interoperation of multiple devices behind a firewall and how to create an auto updater for shelly scripts.

### AIDE - Solar (not available yet)
The second AIDE application could be a technical system that transforms the energy of a solar panel so that it can charge USB devices. It should transmit data about the generated energy to a web host. Automated firmware updates are of course also part of the design.
---

## Human Periodically in the Loop

The classic models of *human-in-the-loop* and *human-out-of-the-loop* are not suitable for AIDE.
The former is not suitable because we thereby degrade the agent to a code-completion editor, the latter is not suitable because everything slips away from us.

<img src="./Loop.jpg" align="left" width="180" style="margin-right: 15px;">

We see *human-sporadically-in-the-loop* and *human-periodically-in-the-loop* as alternatives.
*Sporadically* would mean that the human dives into the world of technical artifacts rather randomly or, for example, on the occasion of an occurring error, identifies problems, perhaps even solves them themselves. However, it turns out that with increasing distance from the code, the human tends to increasingly desperately urge the AI to fix the error. This often results in catastrophic tinkering and superficial fixing, old errors reoccur, and both together lose the ground under their feet. Incidentally, they both tend to gloss over or even deny this circumstance.

Our answer, *human-periodically-in-the-loop*, we derive partly from our own experience, partly from observing industries where the problem has existed for some time that machines can in principle master a process very well, and yet for good reasons we as humans do not want to transfer full responsibility to them.

A good example of this is aviation. It's no coincidence that professional pilots must repeatedly fly landings manually, even though the autopilot might perform a more perfect landing in difficult wind conditions than they themselves would. Professional pilots are quite afraid of checks in the simulator because there they are systematically challenged to the limit of their abilities.

**We derive the following guidelines for *human-periodically-in-the-loop*:**

* The human must fundamentally possess sufficient competence to reliably comprehend at the detail level what the agent suggests or has produced. If a single human cannot do the job, then there must be several of them who are specialized in different technical artifacts (database design, performance optimization, etc.).
* The human must possess sufficient time and self-discipline to repeatedly take deep insights into machine-generated work results at critical points. Since we don't want to rely only on their good will, we must *periodically* compel them to do so. Hence the name.
* There must be reviews by neutral third parties in which both the human and the machine must separately prove that each of them still has everything under control. We must learn to organize this process (quasi the simulator hour for software developers).
* In our opinion also the AI must be challenged because we need to rely on its ability to defend existing arcitecture principles against loss of clarity or corruption. In analogy to "intrusion testing" we have a setting in mind where a human (or an adversarial AI) introduces bad changes into documentation or code and where we expect our trained AI agent to critisize and object.
* Systematization and compulsion are only a safety net. Above all, the human must develop good instincts to recognize critical points. They must sense when it's good to watch the agent's hands very closely. Conversely, they must also recognize when to use it as a partner and advisor or when they can give it complete free rein.
* The human may be happy that the agent takes care of tedious routine tasks, but they must know that they pay a price for it in the form of growing inner distance from technical results (like database definitions or source code). Keeping this distance at the right level - that is the central challenge of AIDE.

---

## AIDE-Techkit : Building Blocks for Platform Construction

A well designed software system clearly separates T-components and A-components, where **T** stands for TECHNICAL Architectue and **A** stands for APPLICATION Domain. Although there may be needs to intermix the physical manifestations of these components within artefacts (like introducing error handling code and logging at many places within the source code) conceptually T and A are different animals.

- To understand WHAT a system does you focus on (A), to understand HOW it does it your focus is on (T). 
- When maintaining a productive system you are more or less captured within (T) and work on extending and changing (A).
- Changing (T) in a running system requires considerable amounts of re-engineerineg effort which in most cases is economically not worth doing - unless your platform depends on external components which come to the end of their supported life time.
- When thinking about a new system the natural focus is on A-requirements but you need to be well aware of T-requirements (often called NFR = non-functional requirements).
- When you start development of a new system you should begin with a rich and stable set of T components and a very tiny piece of A. This is the most critical phase of your project, because mistakes here will be very expensive to correct.

Our long term goal is to *provide T-building blocks for that phase* which work well together and can be selected according to your needs. We call it the AIDE-Techkit. Our idea is to extract almost all application related code from our AIDE systems so that we end up with standardized reusable T-components. Standardized means: They follow a common philosophy and have similar logical APIs although they are implemented differently due to programming language and runtime environment restrictions. 

We assume that your AI assistant will know the AIDE-Techkit and help you to find and integrate the most appropriate building blocks for your intended platform and your NFRs. You will end up with a professional T-system which can be used to implement your minimal valuable solution (MVS) from the A-perspective. Ideally the chosen T-configuration will not change very much during the development of your system.

To give you an example: The AIDE Quiz contains three different mechanisms to support multiple languages: (a) Google Translator embedding, (b) DEEPL pre-translated valuable content which is cached by the application server, (c) thoroughly internationalized (i18n) UI items, system messages etc.
Depending on the profile of you application you should be able to opt-IN or opt-OUT these different approaches.

---

## Consequences for Computer Science Education

We are preparing a paper that outlines the consequences of our findings for computer science education.

## The Authors

* Dr. Gero Scholz
* plus N.N.
* ..
* ..
