# Copilot Instructions for NeuroICU Sequential Rounds

## Project Overview

This is a comprehensive ICU rounding tool designed for neurological intensive care units. The application provides a structured, step-by-step workflow for conducting patient rounds, ensuring thorough assessment and documentation of critical care patients.

## Technology Stack

- **Frontend**: Single-page HTML application with embedded CSS and JavaScript
- **Storage**: Browser localStorage for patient data persistence
- **Deployment**: Static HTML file that runs in any modern web browser

## Key Features

- Sequential 14-step rounding workflow
- Patient census management
- Multi-modal monitoring support (ICP, EVD, cEEG)
- Disease-specific modules (SAH, ICH, Stroke, TBI)
- ABCDEF bundle integration
- Care gap tracking
- Family communication log
- Handoff and Excel export capabilities

## Code Structure

The main application is contained in `neuroICUassistant.html`:
- **CSS**: Embedded styles in `<style>` tag using CSS custom properties
- **HTML**: Single-page app structure with sidebar, main content, and modals
- **JavaScript**: Embedded in `<script>` tag at the end of the document

## Coding Standards

### HTML
- Use semantic HTML5 elements where appropriate
- Maintain consistent indentation (2 spaces)
- Keep accessibility in mind (labels for form elements, proper heading hierarchy)

### CSS
- Use CSS custom properties (variables) for colors and common values
- Follow mobile-first responsive design approach
- Use BEM-like naming conventions for classes

### JavaScript
- Use vanilla JavaScript (no frameworks)
- Store data in localStorage with JSON serialization
- Use meaningful function and variable names
- Keep functions focused and single-purpose

## Testing

Since this is a simple static HTML application, changes should be:
1. Validated by opening `neuroICUassistant.html` in a browser
2. Tested across different patient scenarios
3. Verified that localStorage persists correctly

### Manual Testing Steps
- Open `neuroICUassistant.html` in a browser (Chrome, Firefox, Safari, or Edge)
- Add a test patient with various diagnoses
- Complete the 14-step workflow
- Verify data persists after page reload
- Test export functionality
- Verify no console errors appear

## Making Changes

When modifying this project:
1. Keep the single-file architecture (all code in `neuroICUassistant.html`)
2. Test changes locally by opening the HTML file in a browser
3. Ensure backward compatibility with existing localStorage data
4. Maintain the medical workflow accuracy (14-step rounding process)
5. Follow HIPAA considerations (no PHI should be transmitted; data stays local)

## Security Considerations

This is a healthcare application with important security requirements:
- **Data stays local**: All patient data must remain in browser localStorage only
- **No external transmissions**: Never add code that sends data to external servers
- **No tracking**: Do not add analytics or tracking scripts
- **Input validation**: Sanitize all user inputs to prevent XSS attacks
- **HIPAA compliance**: Any changes must maintain HIPAA considerations

## Medical Context

This tool is designed for healthcare professionals in neuroICU settings. Key medical concepts:
- **GCS**: Glasgow Coma Scale (neurological assessment)
- **ICP**: Intracranial Pressure monitoring
- **EVD**: External Ventricular Drain management
- **cEEG**: Continuous electroencephalography
- **ABCDEF Bundle**: ICU liberation bundle (Assess/prevent pain, Breathing trials, Coordination, Delirium management, Early mobility, Family engagement)

## Common Tasks for Copilot

Good tasks to assign:
- Adding new clinical assessment fields
- Improving UI/UX elements
- Adding new export formats
- Enhancing data validation
- Adding new disease-specific modules
- Improving accessibility
- Fixing bugs in existing functionality
- Refactoring code for clarity
- Updating documentation

Tasks requiring human review:
- Changes to clinical protocols or medical decision logic
- Security-related changes
- Major architectural changes
- Any changes that could affect patient safety calculations
- Modifications to the 14-step rounding workflow order

## Pull Request Guidelines

When reviewing Copilot-generated PRs:
1. Verify that all changes are contained within `neuroICUassistant.html`
2. Test the application by opening the HTML file in a browser
3. Check that localStorage data migration is handled if data structure changes
4. Ensure no external dependencies or network calls are introduced
5. Validate that the medical workflow remains accurate

## File Structure

The repository contains:
- `neuroICUassistant.html` - Main application file (single-page HTML with embedded CSS and JavaScript)
- `index.html` - Redirect page to main application
- `neuroicurounds.html` - Legacy file (empty, redirects to neuroICUassistant.html)
- `README.md` - User-facing documentation
- `PRD.md` - Product Requirements Document
- `.github/copilot-instructions.md` - This file (instructions for Copilot)
- `.github/workflows/` - GitHub Actions for deployment

## Build and Deployment

**No build step required** - This is a static HTML application.

**Deployment**: The application is automatically deployed via GitHub Pages when changes are pushed to the main branch.

**Local Development**: Simply open `neuroICUassistant.html` in a web browser. No server or build process needed.
