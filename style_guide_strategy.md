# Strategy: Akuma Style Guide & Design Exploration

## 1. Purpose & Goals

**Purpose:** To establish a comprehensive, easy-to-use style and builder guide (the "Akuma Style Guide") that ensures consistency, quality, and adherence to brand/UX principles across all applications developed within the "Goodbye Human" no-code environment.

**Goals:**

*   **Consistency:** Ensure all applications share a unified look, feel, and interaction pattern.
*   **Quality:** Promote best practices in UI/UX design and frontend development.
*   **Efficiency:** Provide developers (AI agents) with clear guidelines and reusable components to accelerate development.
*   **Maintainability:** Make applications easier to update and maintain through standardized approaches.
*   **Brand Alignment:** Reinforce the Akuma brand identity.
*   **Flexibility:** Support variations for different application types (starting with web apps).
*   **Evolution:** Allow the guide to be easily updated and reflect the latest UI/UX research and platform needs.

## 2. Location, Format, and Access

*   **Source Repository:** The canonical source for the style guide will be the `akuma-style-guide` GitHub repository (the one targeted by Phase 1 tasks GS-01 to GS-05).
*   **Format:** The guide will be built as a static website using a documentation generator like **VitePress**. This provides a good balance of readability, maintainability, code examples, and search functionality.
*   **Deployment:** The VitePress site will be automatically built and deployed via GitHub Actions to **GitHub Pages** upon changes to the main branch of the repository.
*   **Permanent URL:** GitHub Pages provides a stable, permanent URL. **[Note: This URL will be updated here once the repository is created and the guide is deployed.]**

## 3. Content Structure

The guide will be organized logically, including sections such as:

*   **Introduction:** Vision, principles, how to use the guide.
*   **Brand Identity:** Logo usage, color palette, typography, tone of voice.
*   **Design Principles:** Core UX philosophies (e.g., mobile-first, loyalty-visible, vault-first).
*   **Layout & Grid:** Responsive layout system, spacing, alignment.
*   **UI Components:** Detailed specifications and usage guidelines for common elements (buttons, forms, cards, modals, navigation, etc.). This section will include code snippets (React) and visual examples.
*   **Interaction Patterns:** Guidelines for common user flows (e.g., data display, user input, feedback, navigation).
*   **Accessibility:** Standards and best practices (WCAG).
*   **Application Type Guides:**
    *   **Web Applications (Initial Focus):** Specific guidance for React PWAs, viewport considerations (390x844 base), mobile-specific patterns.
    *   *(Future)* Guides for other types (e.g., CLI tools, backend service standards) can be added as needed.

## 4. Update Process

1.  **Proposal/Change Request:** Anyone can propose changes via GitHub Issues in the `akuma-style-guide` repository.
2.  **Development:** Gl1tchCTRL (or assigned agent) creates a new branch, makes the necessary changes to the documentation/code components within the VitePress site.
3.  **Pull Request (PR):** A PR is submitted to the main branch.
4.  **Preview:** The existing `deploy-preview.yml` workflow (from GS-04/GS-05) should generate a preview deployment of the updated guide.
5.  **Review/Approval:**
    *   **Technical Review:** Forge/0xShadow review any code changes.
    *   **Content/UX Review:** Gl1tchCTRL reviews content. Fungible provides final approval on significant UX/logic changes.
    *   *(Optional)* The dashboard approval workflow (DI-01 to DI-03) can be used for formal sign-off on major updates, linking the preview URL to the dashboard task.
6.  **Merge & Deploy:** Once approved, the PR is merged into the main branch. This automatically triggers the GitHub Action to build and deploy the updated guide to the permanent GitHub Pages URL.

## 5. Enforcement & Integration

*   **CI/CD Integration:**
    *   **Linters:** Standard frontend linters (ESLint, Prettier, Stylelint) configured according to the guide's rules will be included in the project templates and run during CI.
    *   **Component Library:** Reusable React components built according to the guide will be packaged and included in templates, encouraging direct usage.
    *   *(Advanced)* Visual Regression Testing: Tools like Percy or Chromatic could be integrated into CI to automatically detect unintended visual changes, though this adds complexity and cost.
*   **Manual Review:** The dashboard approval workflow provides a gate for manual review of significant UI changes against the style guide, using the preview deployments.
*   **Agent Training:** AI agents will be trained/prompted to consult the style guide URL as the primary reference for UI/UX development.

## 6. Design Exploration & Variations (Mobile Vault/Cap Table Focus)

Addressing the need to quickly view multiple design options based on UI/UX research:

*   **Component Variants:** The core React component library (part of the VitePress setup or a separate package) should be built with **theming and variant support** (e.g., using CSS variables, styled-components theming, or utility classes).
*   **Dedicated Exploration Tool/Section:**
    *   **Option A (Integrated):** Create a specific section within the VitePress style guide site called "Design Explorations" or "Prototypes". Gl1tchCTRL can use this section to build interactive examples showcasing different variants or approaches for specific features (like vault management), referencing the latest research.
    *   **Option B (External Tool):** Utilize tools like Storybook alongside the component library. Storybook excels at isolating and showcasing component variations and allows for rapid prototyping of different states and themes.
*   **Process:**
    1.  **Research:** Gl1tchCTRL conducts UI/UX research.
    2.  **Prototyping:** Gl1tchCTRL uses the component library variants, the "Explorations" section, or Storybook to quickly build interactive mockups of different design options (e.g., 2-3 variations for vault management on mobile).
    3.  **Review:** These prototypes can be shared via URL for rapid review by Fungible/Matt/team.
    4.  **Decision:** Once a direction is chosen, the final design is formally documented in the main style guide.
*   **Benefit:** This allows for rapid iteration and visualization of design concepts *before* committing to full implementation in an application, leveraging the reusable components defined by the guide.

## 7. Roles & Responsibilities

*   **Gl1tchCTRL (Frontend/UX Lead):** Owns the style guide content, component library development, UX research, and design exploration/prototyping.
*   **Forge (DevOps Lead):** Owns the CI/CD pipeline for building, testing, and deploying the style guide website and preview environments.
*   **Manus (Project Manager):** Manages the update process (tracking issues, PRs, approvals), ensures integration with overall project plans.
*   **Fungible (Founder):** Provides final approval on significant UX/logic changes and design directions.
*   **All AI Dev Agents:** Responsible for consulting and adhering to the deployed style guide.
