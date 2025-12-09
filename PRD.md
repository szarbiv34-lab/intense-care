# Product Requirements Document: NeuroICU Sequential Rounds

## 1. Executive Summary

### 1.1 Product Overview
NeuroICU Sequential Rounds is a comprehensive web-based ICU rounding tool designed specifically for neurological intensive care units. The application provides a structured, step-by-step workflow for conducting patient rounds, ensuring thorough assessment and documentation of critical care patients.

### 1.2 Problem Statement
Healthcare professionals in neuroICU settings need a systematic approach to conducting patient rounds that:
- Ensures no critical assessment steps are missed
- Tracks disease-specific protocols (SAH, ICH, Stroke, TBI)
- Manages multi-modal monitoring data (ICP, EVD, cEEG)
- Maintains care gap awareness
- Facilitates handoff communication
- Preserves patient data privacy (HIPAA-compliant local storage)

### 1.3 Target Users
- **Primary**: Neurological ICU physicians (Attendings, Fellows, Residents)
- **Secondary**: Advanced Practice Providers (APPs), ICU Nurses (RNs), Respiratory Therapists (RTs)
- **Tertiary**: PharmD, Physical Therapists, Dietitians, Social Workers

### 1.4 Success Metrics
- Reduction in missed care elements during rounds
- Improved handoff quality and completeness
- Time efficiency in conducting structured rounds
- User adoption rate among neuroICU teams
- Data persistence and reliability

---

## 2. Product Goals & Objectives

### 2.1 Core Goals
1. **Systematic Rounding**: Provide a 14-step sequential workflow that ensures comprehensive patient assessment
2. **Data Persistence**: Maintain patient data locally in browser storage for continuity across sessions
3. **Clinical Decision Support**: Integrate disease-specific modules and protocols
4. **Team Coordination**: Track team presence and role-specific responsibilities
5. **Privacy First**: Ensure all patient data stays local (no external transmission)

### 2.2 Non-Goals
- Electronic health record (EHR) integration
- Cloud-based data synchronization
- Multi-device data sync
- Real-time collaboration features
- Mobile native application

---

## 3. User Stories & Use Cases

### 3.1 Primary User Stories

**As an ICU physician, I want to:**
- Conduct structured rounds following a standardized 14-step workflow
- Track which patients I've completed rounds on
- Document disease-specific assessments (SAH, ICH, Stroke, TBI)
- Identify care gaps and track their resolution
- Export data for handoff or record-keeping

**As an ICU nurse, I want to:**
- Mark my presence on the rounding team
- See which assessment steps require nursing input
- Track ABCDEF bundle compliance
- Document family communication

**As a respiratory therapist, I want to:**
- View respiratory assessment items during rounds
- Track ventilator settings and liberation attempts
- Document spontaneous breathing trials

### 3.2 Key Use Cases

**Use Case 1: Starting Morning Rounds**
1. User opens application
2. Marks team members present
3. Reviews patient census
4. Selects first patient
5. Proceeds through 14-step workflow
6. Marks patient as complete
7. Moves to next patient

**Use Case 2: Adding New Patient**
1. User clicks "Add Patient"
2. Enters patient demographics (Room, Bed, MRN, Age, Sex)
3. Selects primary diagnosis
4. Adds additional diagnoses if needed
5. Patient appears in census list
6. User begins rounding on new patient

**Use Case 3: Identifying Care Gaps**
1. During rounds, user notices missing element
2. User documents care gap in system
3. System highlights gaps during subsequent rounds
4. User marks gap as resolved when complete
5. System tracks gap resolution

**Use Case 4: Handoff Process**
1. User completes rounds on all patients
2. User generates handoff summary
3. System compiles key data points
4. User exports to Excel for offline reference
5. User shares with receiving team

---

## 4. Functional Requirements

### 4.1 Patient Census Management

**FR-1.1**: System shall allow users to add new patients with following fields:
- Room number (required)
- Bed identifier (required)
- Medical Record Number (MRN) (required)
- Age (required)
- Sex (required)
- Primary diagnosis: SAH, ICH, Stroke, TBI, Cardiac Arrest, Other (required)
- Additional diagnoses (optional, multiple)

**FR-1.2**: System shall display patient census in sidebar with:
- Patient name/identifier
- Room and bed location
- Primary diagnosis badge with color coding
- Rounding completion status

**FR-1.3**: System shall allow users to:
- Edit patient information
- Delete patients from census
- Mark patients as complete
- View completion indicator for each patient

### 4.2 Team Management

**FR-2.1**: System shall track team member presence for:
- MD (Attending)
- APP (Advanced Practice Provider)
- RN (Registered Nurse)
- RT (Respiratory Therapist)
- PharmD (Pharmacist)
- PT (Physical Therapist)
- RD (Registered Dietitian)
- SW (Social Worker)

**FR-2.2**: System shall persist team presence across patients during single session

**FR-2.3**: System shall indicate which role typically presents each assessment step

### 4.3 Sequential Rounding Workflow

**FR-3.1**: System shall implement 14-step sequential workflow:

1. **Neuro Assessment** (Presenter: MD)
   - Glasgow Coma Scale (GCS) with E/V/M components
   - Pupil exam (size, reactivity)
   - Motor exam findings
   - Neuro checks frequency

2. **Neuro Diagnostics** (Presenter: MD)
   - ICP monitoring status and values
   - EVD management (if applicable)
   - cEEG monitoring status
   - Imaging findings
   - Disease-specific assessments

3. **Respiratory** (Presenter: RT)
   - Ventilator settings
   - Oxygenation status
   - Spontaneous breathing trial readiness
   - Liberation assessment

4. **Cardiovascular** (Presenter: RN/MD)
   - Hemodynamic status
   - Vital signs tracking
   - Vasoactive medication review
   - Volume status

5. **Lines & Access** (Presenter: RN)
   - Central line assessment
   - Arterial line status
   - Peripheral IV status
   - Line necessity review

6. **Medications** (Presenter: PharmD)
   - Current medication review
   - DVT prophylaxis
   - Stress ulcer prophylaxis
   - Sedation/analgesia
   - Antibiotic stewardship

7. **Labs & Diagnostics** (Presenter: MD)
   - Recent lab results
   - Pending studies
   - Required lab draws

8. **Nutrition** (Presenter: RD)
   - Feeding route
   - Caloric goals
   - Tolerance assessment

9. **ABCDEF Bundle** (Presenter: RN)
   - Assess, prevent, and manage pain
   - Both spontaneous awakening and breathing trials
   - Choice of sedation
   - Delirium assessment (CAM-ICU)
   - Early mobility
   - Family engagement

10. **Mobility & Therapy** (Presenter: PT)
    - Mobility level
    - Therapy orders
    - Equipment needs
    - Safety considerations

11. **Psychosocial** (Presenter: SW)
    - Family communication log
    - Goals of care documentation
    - Discharge planning needs

12. **Disposition** (Presenter: MD)
    - ICU day number
    - Expected length of stay
    - Discharge barriers
    - Transfer planning

13. **Care Gaps** (Presenter: Team)
    - Identified care gaps
    - Gap categorization
    - Resolution tracking
    - Responsible party assignment

14. **Summary & Plan** (Presenter: MD)
    - Problem list
    - Assessment and plan for each problem
    - Key action items
    - Follow-up items

**FR-3.2**: System shall allow users to:
- Navigate between steps using progress indicators
- Jump to specific steps via step navigation
- Mark individual assessment items as complete
- See progress percentage across all steps

**FR-3.3**: System shall validate required fields before marking patient as complete

### 4.4 Disease-Specific Modules

**FR-4.1**: For SAH (Subarachnoid Hemorrhage) patients, system shall track:
- Hunt-Hess grade
- Fisher scale
- Vasospasm monitoring
- Aneurysm treatment status
- Nimodipine administration

**FR-4.2**: For ICH (Intracerebral Hemorrhage) patients, system shall track:
- ICH score
- Hematoma location and size
- Expansion risk factors
- Blood pressure goals
- Reversal status (if anticoagulated)

**FR-4.3**: For Stroke patients, system shall track:
- NIHSS score
- Stroke type (ischemic/hemorrhagic)
- tPA administration status
- Thrombectomy status
- Secondary prevention measures

**FR-4.4**: For TBI (Traumatic Brain Injury) patients, system shall track:
- Injury mechanism
- Injury pattern
- Marshall CT classification
- ICP management
- Seizure prophylaxis

### 4.5 Data Persistence & Export

**FR-5.1**: System shall automatically save all data to browser localStorage

**FR-5.2**: System shall persist data across browser sessions

**FR-5.3**: System shall provide data export functionality:
- Excel format for census and patient data
- Handoff summary format
- Include all assessment data

**FR-5.4**: System shall not transmit any data to external servers

### 4.6 Care Gap Tracking

**FR-6.1**: System shall allow users to:
- Add new care gaps during any step
- Categorize gaps by type
- Assign responsible party
- Set priority level

**FR-6.2**: System shall track:
- Gap identification date/time
- Gap description
- Gap status (open/resolved)
- Resolution date/time

**FR-6.3**: System shall display active care gaps prominently during rounds

---

## 5. Non-Functional Requirements

### 5.1 Performance

**NFR-1.1**: Application shall load within 3 seconds on standard hardware

**NFR-1.2**: UI interactions shall respond within 200ms

**NFR-1.3**: Data save operations shall complete within 500ms

### 5.2 Usability

**NFR-2.1**: Application shall be usable without training for healthcare professionals familiar with ICU rounding

**NFR-2.2**: Application shall provide clear visual indicators for:
- Current step in workflow
- Completed assessment items
- Required vs optional fields
- Alert conditions

**NFR-2.3**: Application shall be responsive and usable on tablets and desktop devices

### 5.3 Reliability

**NFR-3.1**: Application shall prevent data loss through automatic saving

**NFR-3.2**: Application shall gracefully handle localStorage quota limits

**NFR-3.3**: Application shall provide error messages for invalid data entry

### 5.4 Security & Privacy

**NFR-4.1**: Application shall store all data locally in browser localStorage only

**NFR-4.2**: Application shall not transmit any patient data to external servers

**NFR-4.3**: Application shall not include analytics or tracking scripts

**NFR-4.4**: Application shall sanitize all user inputs to prevent XSS attacks

**NFR-4.5**: Application shall maintain HIPAA considerations for local data storage

### 5.5 Compatibility

**NFR-5.1**: Application shall run in modern browsers:
- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

**NFR-5.2**: Application shall not require internet connectivity

**NFR-5.3**: Application shall work as a standalone HTML file

### 5.6 Maintainability

**NFR-6.1**: Application shall maintain single-file architecture (HTML with embedded CSS/JS)

**NFR-6.2**: Code shall follow consistent formatting and naming conventions

**NFR-6.3**: Application shall maintain backward compatibility with existing localStorage data

---

## 6. User Interface Requirements

### 6.1 Layout Structure

**UI-1.1**: Application shall use sidebar + main content layout:
- Left sidebar: Team presence + Patient census (280px fixed width)
- Main content: Patient assessment workflow (responsive flex)

**UI-1.2**: Main content area shall include:
- Header with patient information
- Progress bar showing completion percentage
- Step navigation with numbered indicators
- Content area with current step
- Navigation footer with prev/next buttons

### 6.2 Visual Design

**UI-2.1**: Application shall use consistent color scheme:
- Primary: Blue (#1e40af, #3b82f6)
- Success: Green (#059669)
- Warning: Orange (#d97706)
- Danger: Red (#dc2626)
- Disease-specific colors for diagnoses

**UI-2.2**: Application shall use clear visual hierarchy:
- Large headings for major sections
- Icon indicators for section types
- Badge indicators for roles and statuses
- Color-coded alerts and warnings

**UI-2.3**: Application shall provide visual feedback for:
- Completed items (checkmarks, strikethrough)
- Active selection (border highlighting)
- Alert conditions (colored backgrounds)
- Progress (progress bar, step indicators)

### 6.3 Responsive Design

**UI-3.1**: On mobile/tablet (≤768px):
- Sidebar becomes bottom sheet
- Main content takes full width
- Team section hidden by default
- Touch-friendly button sizes

**UI-3.2**: On desktop (>768px):
- Sidebar visible at left
- Full team presence grid visible
- Multi-column layouts for data entry

### 6.4 Accessibility

**UI-4.1**: Application shall provide:
- Proper label associations for form inputs
- Semantic HTML5 elements
- Sufficient color contrast ratios
- Keyboard navigation support

---

## 7. Technical Architecture

### 7.1 Technology Stack

**Single-Page HTML Application:**
- HTML5 for structure
- CSS3 with custom properties for styling
- Vanilla JavaScript for functionality
- No external dependencies or frameworks

### 7.2 Data Model

**Patient Object:**
```javascript
{
  id: string (UUID),
  room: string,
  bed: string,
  mrn: string,
  age: number,
  sex: string,
  primaryDx: string,
  additionalDx: array,
  completed: boolean,
  createdAt: timestamp,
  assessmentData: {
    step1: { ... },
    step2: { ... },
    // ... steps 3-14
  }
}
```

**Session Object:**
```javascript
{
  date: timestamp,
  teamPresent: array,
  patients: array,
  activePatientId: string
}
```

### 7.3 Storage Strategy

**localStorage Keys:**
- `neuroicu_patients`: Array of patient objects
- `neuroicu_session`: Current session data
- `neuroicu_settings`: User preferences

**Storage Management:**
- Automatic save on data change
- Lazy loading for large datasets
- Data validation before save
- Migration strategy for schema changes

### 7.4 Deployment

**Distribution Method:**
- Single HTML file
- No build process required
- No server dependencies
- GitHub Pages for optional web hosting

---

## 8. Implementation Phases

### Phase 1: Core Functionality (Complete)
- [x] Patient census management
- [x] Team presence tracking
- [x] 14-step sequential workflow
- [x] Basic data persistence
- [x] Navigation and progress tracking

### Phase 2: Enhanced Features (Complete)
- [x] Disease-specific modules
- [x] ABCDEF bundle integration
- [x] Care gap tracking
- [x] Family communication log
- [x] Excel export functionality

### Phase 3: Refinement & Optimization (Future)
- [ ] Enhanced mobile experience
- [ ] Offline data backup/restore
- [ ] Printable round sheets
- [ ] Customizable workflow steps
- [ ] Additional disease modules

### Phase 4: Advanced Features (Future)
- [ ] Clinical calculators (VISAGE, etc.)
- [ ] Trend visualization for vitals
- [ ] Template library for common scenarios
- [ ] Multi-language support
- [ ] Voice input capabilities

---

## 9. Constraints & Assumptions

### 9.1 Constraints

**Technical Constraints:**
- Single-file HTML architecture must be maintained
- No external dependencies or frameworks
- No server-side processing
- Browser localStorage size limits (typically 5-10MB)

**Privacy Constraints:**
- No external data transmission
- No cloud storage
- No analytics or tracking
- HIPAA compliance for local storage

**User Constraints:**
- Users must use same browser/device for data persistence
- Users responsible for data backup via export
- No multi-user collaboration features

### 9.2 Assumptions

**User Assumptions:**
- Users have basic computer literacy
- Users understand medical terminology
- Users have access to modern web browser
- Users understand data remains local only

**Environmental Assumptions:**
- Stable browser environment
- Sufficient device storage
- Users won't clear browser data during active session
- Single user per browser instance

**Clinical Assumptions:**
- 14-step workflow aligns with neuroICU best practices
- Disease categories cover majority of neuroICU patients
- ABCDEF bundle remains standard of care
- Assessment items reflect current medical standards

---

## 10. Risks & Mitigations

### 10.1 Technical Risks

**Risk: Browser localStorage data loss**
- Mitigation: Auto-save frequently, provide export functionality, user education

**Risk: Browser compatibility issues**
- Mitigation: Test across major browsers, use standard web APIs, graceful degradation

**Risk: localStorage quota exceeded**
- Mitigation: Data compression, old data archival, quota monitoring

### 10.2 User Experience Risks

**Risk: Users skip critical assessment steps**
- Mitigation: Required field validation, visual progress indicators, step completeness checks

**Risk: Data entry fatigue**
- Mitigation: Smart defaults, copy-forward functionality, quick-entry shortcuts

**Risk: Learning curve for new users**
- Mitigation: Intuitive UI, inline help text, role-based cues

### 10.3 Clinical Risks

**Risk: Outdated clinical protocols**
- Mitigation: Regular review with clinical stakeholders, version documentation, update process

**Risk: Misinterpretation of clinical data**
- Mitigation: Clear field labels, contextual help, disclaimer about clinical judgment

**Risk: Over-reliance on tool vs clinical assessment**
- Mitigation: Tool positioned as documentation aid, not decision-making system

### 10.4 Privacy/Security Risks

**Risk: PHI exposure via localStorage**
- Mitigation: User education, secure device policies, data export warnings

**Risk: Shared device access**
- Mitigation: User responsibility documentation, session management

**Risk: Data corruption**
- Mitigation: Input validation, data integrity checks, backup/restore functionality

---

## 11. Success Criteria

### 11.1 Launch Criteria
- [ ] All 14 steps implemented and functional
- [ ] Patient census management working
- [ ] Data persistence verified
- [ ] Export functionality working
- [ ] Cross-browser testing complete
- [ ] Clinical review completed
- [ ] User documentation available

### 11.2 Success Metrics (3-month post-launch)
- 80% of neuroICU team uses application regularly
- Average of 15 minutes per patient for complete rounds
- 90% completion rate for all assessment steps
- Zero data loss incidents
- User satisfaction score >4.0/5.0
- 50% reduction in missed care elements

### 11.3 Quality Metrics
- Zero critical bugs in production
- <5 minor bugs per release
- 100% of required fields validated
- <200ms response time for UI interactions
- 100% data persistence accuracy

---

## 12. Appendices

### 12.1 Glossary

**ICU**: Intensive Care Unit - specialized hospital unit for critically ill patients

**NeuroICU**: Neurological Intensive Care Unit - ICU specialized for neurological conditions

**GCS**: Glasgow Coma Scale - assessment tool for level of consciousness (3-15 scale)

**ICP**: Intracranial Pressure - pressure inside the skull

**EVD**: External Ventricular Drain - catheter to drain cerebrospinal fluid

**cEEG**: Continuous electroencephalography - brain wave monitoring

**SAH**: Subarachnoid Hemorrhage - bleeding in space surrounding brain

**ICH**: Intracerebral Hemorrhage - bleeding within brain tissue

**TBI**: Traumatic Brain Injury - brain injury from external force

**ABCDEF Bundle**: ICU liberation bundle (Assess pain, Breathing trials, Coordination, Delirium, Early mobility, Family)

**CAM-ICU**: Confusion Assessment Method for ICU - delirium screening tool

**NIHSS**: National Institutes of Health Stroke Scale - stroke severity assessment

**MRN**: Medical Record Number - unique patient identifier

**APP**: Advanced Practice Provider (NP or PA)

**DVT**: Deep Vein Thrombosis

**PHI**: Protected Health Information

**HIPAA**: Health Insurance Portability and Accountability Act

### 12.2 References

- American Heart Association/American Stroke Association Guidelines
- Neurocritical Care Society Guidelines
- Society of Critical Care Medicine ABCDEF Bundle
- Brain Trauma Foundation TBI Guidelines
- Hunt-Hess Subarachnoid Hemorrhage Grading Scale
- Fisher Scale for SAH
- ICH Score for Intracerebral Hemorrhage
- Marshall CT Classification for TBI

### 12.3 Change Log

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 2025-12-09 | Initial | Initial PRD creation |

---

## Document Control

**Document Owner**: Product Team

**Last Updated**: 2025-12-09

**Review Cycle**: Quarterly

**Stakeholders**:
- Clinical team (MD, APP, RN, RT, PharmD, PT, RD, SW)
- Development team
- Hospital administration
- Quality/Safety committee

**Approval Required From**:
- Medical Director, NeuroICU
- Nursing Director, NeuroICU
- Chief Medical Information Officer
- Privacy/Security Officer
