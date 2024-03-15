# The Importance of Web Accessibility

-   Accessibility is about removing barriers. It ensures technology is usable by people with disabilities (those who can't see, can't use a mouse, navigate by voice, etc.).
-   Accessibility is a civil right. It's about upholding everyone's right to digital access.
-   Accessibility is good for business. While there's an upfront cost, not investing in it leads to:
    -   Costly reworks or re-platforming
    -   Difficulty maintaining code
    -   Legal risks & compliance issues
    -   Potential loss of market share

# Why is Accessibility Important?

-   The right thing to do: Upholds civil rights and creates a more inclusive digital landscape.
-   Sign of quality software: Accessibility practices make code more robust and maintainable.
-   Business benefit: Reduces long-term costs, mitigates legal risk, and can improve market position.

# Motivations to Learn About Accessibility

-   Personal interest: Curiosity about inclusive design.
-   Career growth: A valuable skillset for developers.
-   Professional requirement: Accessibility is becoming non-negotiable in many industries.

# Accessibility Oversights: Common Even in Thoughtful Design

-   Importance of Keyboard Navigation: A well-designed website may exhibit accessibility improvements but might still fall short in areas such as keyboard-only navigation of dropdowns. Thorough testing remains essential throughout the development process.
-   Auto-Animating Widgets: Auto-animating widgets should include a pause option to respect accessibility guidelines. They should respond to user preferences for reduced motion, offering a non-distracting experience.
-   Missing Interactive Roles: Using non-interactive elements without proper roles (like `button`) prevents screen readers from correctly identifying and announcing UI components.
-   Positive Examples: Some websites demonstrate strong accessibility with features like skip links and well-designed keyboard-navigable widgets. These can serve as models for improvement.

# Key Takeaways:

-   Accessibility is often overlooked, even in well-intentioned projects. This can be due to:
    -   Lack of prioritized accessibility testing
    -   Insufficient QA processes
    -   A general lack of awareness within the development team
-   Keyboard-first testing is crucial. Many accessibility issues can be identified simply by navigating the site with the keyboard (Tab, Enter, Escape keys).
-   Understanding proper HTML semantics and roles is essential. Using the correct elements and interactive roles ensures components are accessible from the start.

# Accessibility in Minimum Viable Products (MVPs)

-   The Importance of Early Accessibility: Planning for accessibility from the start prevents costly rework and ensures a usable experience for everyone. Think of it like the skateboard to car analogy -- ship something smaller but functional, then build on it.
-   Don't Use Overlays: Quick-fix overlays don't provide true accessibility.
-   The Steep Cost of Technical Debt: Accessibility issues become significantly more expensive to fix later in the development process. Planning ahead saves money and resources.
-   Shift Left: "Shift left" means prioritizing accessibility in every phase (planning, design, engineering, content strategy) to catch problems early.

# Prioritizing Accessibility Fixes

To help focus effort, prioritize accessibility problems based on:

-   Impact: How severely does the issue hinder a user's ability to complete tasks? Does it violate accessibility standards (WCAG)?
-   Usage: Is the issue on a core user flow with significant traffic?
-   Platforms: Does the problem need platform-specific solutions or design tweaks?
-   Cost of Inaction: Estimate the possible financial consequences of not fixing the issue (loss of sales, legal risks, etc.).


# Foundations of Accessible User Interfaces

-   Accessibility is Always Important: Emphasize the basics, as even simple mistakes can have a significant impact later on.
-   Design with Access in Mind: Consider accessible UI choices early in the design process:
    -   Clear visual hierarchy
    -   Intuitive interactions
    -   User testing with individuals who use assistive technologies
-   Semantic HTML: Building blocks of accessible UIs
    -   Headings (H1-H6): Structure content, aiding screen reader navigation. Prioritize meaning, not appearance, styling is done with CSS.
    -   Landmark Elements: Define page sections (`main`, `nav`, `footer`, etc.). Use `aria-label` and `aria-labelledby` to provide labels for clarity.
    -   Lists: Logically group items for screen reader organization.
-   Keyboard Interactivity: If a mouse can do it, the keyboard must as well.
    -   Button Element: Use the native `<button>` for built-in keyboard behavior and accessibility features.
-   ARIA: Use ARIA only when necessary to supplement native HTML, never replace it. We'll cover this in more detail later.

-   Form Labels: Spans used instead of `<label>` tags.
    -   Why: Screen readers need correctly associated labels for form inputs. Placeholders aren't always reliable.
    -   Fix: Use `<label>` and `for` attributes (or nest the input within the label).
-   Custom Controls: Divs or other elements used in place of standard buttons, checkboxes, etc.
    -   Why: Native HTML controls have built-in accessibility. Reinventing the wheel risks missing key features.
    -   Fix: Where possible, use standard HTML controls. If customization is absolutely necessary, ensure the custom control mimics all expected behaviors for keyboard and screen readers.
-   Colors and Contrast: Visibly low contrast between text and background elements.
    -   Why: Insufficient contrast makes content hard to read, especially for those with low vision.
    -   Fix: Use contrast checkers and tools like accessible color palette generators. Follow WCAG contrast ratio guidelines.
-   Modals and Layers: Custom modal implementations.
    -   Why: Homemade modals can lack proper focus management, keyboard accessibility, and ARIA roles that signal their function to screen readers.
    -   Fix: Leverage accessible modal libraries, or thoroughly test custom implementations for focus trapping, role assignment, and keyboard navigation.
-   Click Events on Divs: Use of `onclick` on non-interactive elements like divs, especially for core actions.
    -   Why: Divs aren't inherently interactive. Screen readers won't announce them and they can't be triggered without a mouse.
    -   Fix: Use native `<button>` elements for actions. If customization is necessary, add ARIA roles and keyboard event listeners.
