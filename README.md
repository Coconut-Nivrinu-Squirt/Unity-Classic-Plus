# Unity Classic Plus
## A history-first evolution of an efficient desktop environment
### Version 0 (Source Archive)
Unity Classic Plus aims to preserve the Unity desktop environment while evolving it from its Canonical-era foundation, modernizing the implementation while remaining faithful to the user-first experience that originally defined Unity.
As part of this philosophy, future development may explore a desktop-centric convergence model once the project's foundation is stable, well understood, and maintainable.
### Core project values
- Preservation before Modernization.
    - The existing code should be understood and documented before major changes are made.
    - Historical code shall be documented and understood before being modified.
    - Code that is not understood shall not be modified without first understanding it.
    - Historical behaviour should be documented and understood before modification unless it is not practical to do so.
- Documentation is key
    - Without understandable documentation, technical debt is inherited and not understood.
    - Significant changes to the codebase must come with attached documentation and a description of the expected user benefits.
    - Future maintainers must be able to interpret what a codebase modification does and why it exists without guesswork.
    - Source origins must remain traceable.
    - Historical attribution must be preserved.
- User Experience First
    - User-facing functionality must operate smoothly.
    - Developer convenience shall not come at the expense of a user's experience.
    - Any changes made should benefit the user.
    - A user should be able to understand the codebase and become a maintainer if they choose to do so.
- Performance is part of the user experience
    - A user should be able to run this desktop environment on older hardware.
    - Resource consumption must be considered against low-end specifications.
    - Performance regressions should be treated as damaging to the user experience.
    - Features must justify their resource costs.
- Accessibility first
    - Accessibility is not an optional enhancement. It is a core component of the project.
    - Accessibility helps open up the Linux ecosystem to those who need accessibility tools.
    - Accessibility regressions are functional regressions.
    - Orca is a beneficial dependency because it is better than starting a screen reader from scratch.
        - Contribute Orca fixes upstream first to prevent patch clutter within Unity Classic Plus.
        - Forking is a last-resort option.
- Patches are a last-resort option.
    - Finding the root cause of an issue should come first.
    - Long-term patches should be considered temporary solutions when practical and must be well documented.
    - If a fix must go upstream to make a specific application more compliant with standards, a PR should be opened with the respective project.
    - If the fix belongs in Unity Classic Plus, the fix should not be applied as a patch. It should instead be built into the respective application or component containing the issue.
    - Compiler warnings and deprecation warnings are to be treated as functional regressions.
- Distribution-Agnostic Design Values
    - It should be possible to clone this project on any distribution, install the respective dependencies, and build it.
    - If a dependency requires a specific distribution, it should be avoided.
    - If a dependency starts to require patches, upstream fixes should be attempted first. If upstream fixes do not work out, forking may be considered.
- Convergence for Companionship, Not Replacement.
    - Convergence exists to provide additional functionality to the desktop, not replace it.
        - If companion functionality duplicates desktop functionality without providing meaningful added value to the companion device and/or desktop, the companion device is no longer acting as a companion device.
    - The companion device should still function as an independent device.
    - Companion devices must not rely on servers that are not operated by the user.
    - Companion functionality is local-only by default and does not require a cloud account.
        - Forced Internet connectivity breaks the local-only default functionality.
    - Remote access to companion functionality must be set up by the end user.
    - Cloud services or accounts must not be required for convergence functionality.
### Where is the original README?
The original README did not contain the level of documentation detail required to facilitate V0, but it has been preserved and can be found here:
[Archive/README](Archive/README)
### Contribution Policy
V0 contains no additions to its AUTHORS file because it is an archival copy. Since no new code has been added, there is no reason to add contributors.
Starting with V1 of the project, contributions are welcome.
Contributors who wish to contribute shall add themselves to the AUTHORS file using the name, alias, or online identity by which they wish to be recognized by others within the project.
### Why 7.4.0?
To see the reasoning behind this chosen baseline, please see:
[7.4.0_BASE_REASONS.md](Archive/7.4.0_BASE_REASONS.md)
### Development test systems in play
Overall requirements between all systems:
- All systems must pass accessibility experience testing.
    - Screen reader software must function.
        - Screen reader crashes must be recoverable using the initial screen reader enable key combination.
            - Screen reader crashes must not be silent.
        - Enabling or disabling the screen reader must be accompanied by a timely audio prompt.
        - The screen reader enable key combination must not require manual configuration.
        - Screen reader defaults must be pleasant forings must be configurable using the screen reader.
        - The screen reader must be accessible from the login screen.
        - Screen reader accessibility must extend to disk-encryption prompts in the future.
    - Terminal-based accessibility settings being the best way to adjust the screen reader is an instant failure.
    - The system must be navigable using audio prompts.
        - Audio prompts must be responsive to user actions.
        - Audio feedback should follow the user's navigation.
            - Navigation feedback may come from any supported input method.
        - Highlighting text should speak the underlying text.
        - Revisiting an item that has already been spoken must produce the same result.
    - Interface elements must be discoverable using accessibility tools.
    - Frustration caused by the accessibility tool is considered an instant failure and must be investigated.
    - Accessibility features must notify the user of their presence once per boot. Users must be able to disable these notifications if they are already aware of the features' existence.
        - The prompt must be audio-based and usable as a pointer to the accessibility settings.
            - The audio prompt must also be pleasant to experience.
            - The accessibility notification must not fail the user if the screen reader enable key combination is changed.
    - Accessibility must remain operational after a system update.
    - Device insertion and removal shall provide audio feedback.
        - Audio feedback should include a basic device description.
- If an accessibility function does not operate on a single system, it is a failure of all development systems.
Main development system:
- Modern multi-core, multithreaded CPU
    - Allows fast compilation and testing of new revisions.
- Plenty of RAM
    - Helps ensure that the latest revision can be compiled without crippling the development system's performance.
- Modern GPU
    - Ensures that the graphics stack is rendered quickly and that animations remain smooth.
- NVMe SSD
    - Ensures that the CPU can quickly retrieve stored binaries used by the desktop environment.
Mobile test system:
- Older CPU
    - Restricts the instruction rate available while compiling and running the desktop environment, helping validate acceptable performance.
- Limited RAM
    - Constrains how much working space the desktop environment has and helps expose feature creep or scope creep.
- Older GPU
    - Ensures that the graphics stack does not suffer from performance issues on older hardware and helps keep the desktop environment responsive.
- SATA SSD
    - Ensures that the system can retrieve binaries at a reasonable speed without relying on NVMe-class storage.
- Battery-based testing
    - The battery should not drain extremely quickly merely from logging into the desktop environment. The login screen should not hide battery information.
Older desktop test system:
- Older CPU
    - Restricts the instruction rate available while compiling and running the desktop environment, helping validate acceptable performance.
- Limited RAM
    - Constrains how much working space the desktop environment has and helps expose feature creep or scope creep.
- Older GPU
    - Ensures that the graphics stack does not suffer from performance issues on older hardware and helps keep the desktop environment responsive.
- SATA HDD or IDE HDD
    - Acts as an extreme benchmark for system performance. If the desktop does not feel responsive while loading binaries from a hard drive, efficiency is being lost somewhere in the process.
## Project roadmap
### Roadmap Notes
This roadmap purposefully does not contain every future version, allowing some flexibility because the project's future requirements cannot be perfectly predicted.
Any versions listed in V0's README are foundational roadmap entries.
Foundational roadmap entries cannot be removed or have their version Focus AND Intended Features AND Success Criteria substantially altered from their V0 entries. Spelling corrections, grammar corrections, formatting corrections, or factual inaccuracies may be corrected as long as the intent of the V0 foundational roadmap entries is not lost.
This helps keep the listed foundational versions on the path intended from the project's beginning. Completion Status is excluded because it must change to reflect version progress.
New versions after V0 may be added after the final foundational roadmap entry if they meet the following criteria:
- The version number is higher than the final foundational roadmap entry.
- The Focus is clearly stated.
- The Intended Features to Be Added are clearly stated.
- The Success Criteria are clearly stated.
- The Completion Status is initially recorded as "Planned".
- The version does not attempt to roll back previously implemented features UNLESS a feature is proven to contain harmful loopholes. The feature removal must be documented and must FORCE A NEW VERSION.
- New features must adhere to the core values stated in V0.
- A proposed new feature must add value to the user experience.
- A proposed new feature must improve existing functionality or address a documented limitation.
- Roadmap additions shall not introduce Internet-connected features.
    - This project focuses on desktop functionality, accessibility, performance, portability, maintainability, and desktop-companion convergence between trusted devices on the same network. Features dependent on consistent Internet connectivity or manual Internet synchronization shall be considered invalid roadmap additions.
    - Features involving package management and Flatpaks are allowed.
        - The feature must support local, non-cloud-connected software management.
These Roadmap Notes are considered part of the initial V0 project constitution. The Roadmap Notes may be corrected for spelling, grammar, formatting, or factual inaccuracies. The intent of the V0 Roadmap Notes may not be lost.

| Version | Focus | Intended Features to Be Added | Success Criteria | Completion Status |
| ----------- | ----------- | ----------- | ----------- | ----------- |
| V0 | Archival foundations | None | Canonical Unity 7.4.0 is archived with properly adjusted documentation. | Completed |
| V1 | Build desktop environment foundations | None | The desktop environment builds without distribution-specific requirements, functions with its existing features, and has its discovered build assumptions and dependencies documented. | Dependency Audit Pass 1 Complete. No code changes yet, Collecting inital dependencies that do not have active maintainership. |
| V2 | Stabilize and simplify necessary code | Basic accessibility, with screen reader functionality work beginning | Unnecessary runtimes causing bloat are removed, and a basic accessibility implementation is started and functional. | Planned |
| V3 | Improve accessibility integration | Moderate-to-high accessibility | 50% of accessibility experience testing passes with no instant failures. | Planned |
| V4 | Finalize accessibility integrations and begin performance improvements | Near-perfect accessibility; low-end systems should not suffer performance issues | All accessibility experience testing passes with no instant failures. The hard-drive-based testing system does not feel sluggish during use, even with accessibility features enabled. | Planned |
| V5 | Begin Software Center revival | Implement a Flatpak-based Software Center | Flatpaks can be managed within the Software Center, and accessibility functions correctly within the Software Center. | Planned |
| V6 | Begin distribution-specific Software Center implementation | Implement distribution detection for the local package-management system while ensuring that accessibility requirements continue to be met | Packages can be managed from within the Software Center. Accessibility tests continue to pass with no instant failures. Software trust-source details and AUR safety information are shown to the user. | Planned |
| V7 | Expand accessibility beyond desktop environment components | Add accessible disk-unlock prompts and similar functionality to the boot process | Accessibility tests pass with no failures during boot, and accessibility services continue functioning after boot. | Planned |
| V8 | Work on implementing Wayland support | Make Wayland usable for the login screen and desktop environment where supported | The Wayland environment loads and provides the same experience as Xorg. Xorg is not phased out for compatibility reasons and is selected automatically where Wayland is not well supported. Accessibility testing passes with no instant failures. | Planned |
| V9 | Modernize Compiz | Upgrade Compiz to be modern and efficient by using the best graphics API available to the installed system at the time | Compiz keeps its look and feel while improving performance. Animations, workspace behaviour, and window management feel the same as they did before Compiz modernization while performance and maintainability increase. Wayland and Xorg continue to function normally. | Planned |
| V10 | Begin work on convergence features | Build a basic convergence application that can bridge texts and SMS/RCS messages in a manner similar to existing solutions | All accessibility experience testing passes with no instant failures. The basic convergence application functions as expected, and SMS/RCS messages can be read using the desktop accessibility software. | Planned |
| V11 | Expand convergence application functionality | Allow the convergence application to handle phone notifications and basic caller information, and allow the computer to act as a Bluetooth headset for the phone | Desktop accessibility functions continue to pass with no instant failures. Caller announcements work with accessibility functions, and phone notifications can be read using the same accessibility software. | Planned |
