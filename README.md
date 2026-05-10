# Kidmans Partners - Website Wireframes

A comprehensive collection of low-fidelity HTML wireframes for the Kidmans Partners website redesign project.

## Project Overview

This project contains 14 interactive HTML wireframes designed to guide the development of the Kidmans Partners website. The wireframes are built with mobile-first responsive design, annotation toggles for designer notes, and consistent brand guidelines across all pages.

## Directory Structure

```
kidmans-wireframes/
├── index.html                    # Master index / dashboard
├── README.md                     # This file
└── pages/
    ├── homepage.html             # Homepage with updated copy
    ├── service-hub.html          # Service directory (8 services)
    ├── industries-hub.html       # Industry directory (9 industries)
    ├── master-service.html       # Service template (reusable)
    ├── business-advisory.html    # Business Advisory with lifecycle tabs
    ├── finance-lending.html      # Finance & Lending split layout
    ├── wealth-management.html    # Wealth Management with interactive carousel
    ├── master-industry.html      # Industry template (reusable)
    ├── payments-hub.html         # Payment options directory
    ├── audit-payments.html       # Audit payment form
    ├── about.html                # About company page
    ├── memberships.html          # Advisory memberships pricing
    ├── careers.html              # Careers / job listings
    └── meet-our-people.html      # Team directory
```

## Features

### Responsive Design
- **Desktop**: 1200px+ (4-column grids, full layouts)
- **Tablet**: 768px - 1199px (2-column grids, adjusted spacing)
- **Mobile**: <768px (1-column stacks, optimized touch targets)

### Annotation Toggle
Every page includes a **"Show Annotations"** button in the top-right corner that toggles designer notes on/off. These notes include:
- Component specifications (sizing, spacing, colors)
- Typography guidelines
- Animation/interaction requirements
- Mobile-specific considerations
- Integration notes for Elementor/WordPress

### Brand Consistency
All pages follow the approved brand guidelines:
- **Color Palette**: Deep Charcoal (#2E2E2E), Off-White (#F5F5F5), Teal (#00A0B0), Gold (#D4A574), Blue (#003D7A)
- **Typography**: Playfair Display (headings), Inter (body)
- **Geometry**: Sharp corners (border-radius: 0)
- **Global Elements**: Navigation bar, footer, brand logo

### Self-Contained HTML
Each page is a standalone HTML file with:
- Embedded CSS (no external stylesheets)
- Embedded JavaScript (for interactions like tabs, carousels)
- No external dependencies
- Can be opened directly in a browser

## Page Descriptions

### Priority 1: Enhanced Core Pages (8 pages)

1. **Homepage** - Updated value proposition ("One Master Plan. Fewer Gaps."), social proof, integrated services grid, testimonials, newsletter signup
2. **Service Hub** - 8-service grid with feature lists and cross-linking capabilities
3. **Industries Hub** - 9-industry grid with sector-specific expertise messaging
4. **Master Service Template** - Reusable template for individual service pages (e.g., Business Advisory, Wealth Management)
5. **Business Advisory & Mentoring** - Lifecycle tabs (Start-ups, Established, Exit-focused) + service features
6. **Finance & Lending** - Split layout for Business vs Residential lending
7. **Wealth Management** - Interactive carousel showing the 13-step advice process
8. **Master Industry Template** - Reusable template for individual industry pages

### Priority 2: New Pages (6 pages)

9. **Payments Hub** - Directory routing to Accounting or Audit payment portals
10. **Audit Payments** - Payment form template for audit invoices
11. **About** - Company story, values, key statistics
12. **Our Memberships** - 3-tier advisory membership pricing comparison
13. **Careers** - Culture messaging + job listings directory
14. **Meet Our People** - Team directory with filterable cards

## How to Use

### Viewing Wireframes
1. Open `index.html` in a web browser to access the master index
2. Click on any page link to view the wireframe
3. Use the **"Show Annotations"** button to toggle designer notes on/off

### Elementor Implementation Notes
- All wireframes are designed to be buildable within Elementor Pro + Plus/Essential add-ons
- Carousel sections use standard Elementor carousel widgets or Swiper.js
- Tab sections use Elementor's native tabs widget
- All animations are CSS-based for maximum compatibility

### Content Customization
- Placeholder text is clearly marked with brackets `[like this]`
- Replace with actual content from the SEO & Content Strategy document
- Images should be sourced from brand guidelines and client-provided assets

## Design System Reference

| Element | Value |
|---------|-------|
| Primary Color | #00A0B0 (Teal) |
| Secondary Color | #D4A574 (Gold) |
| Dark Color | #003D7A (Deep Blue) |
| Neutral Dark | #2E2E2E (Charcoal) |
| Neutral Light | #F5F5F5 (Off-White) |
| Heading Font | Playfair Display, 700 weight |
| Body Font | Inter, 400 weight |
| Border Radius | 0 (sharp corners) |

## Next Steps

1. **Design Review**: Share wireframes with stakeholders for feedback
2. **Content Collation**: Gather final copy for all pages
3. **Asset Preparation**: Collect high-quality images and logos
4. **Elementor Build**: Implement wireframes in Elementor Pro
5. **User Testing**: Validate navigation and conversion flows
6. **Deployment**: Deploy to staging environment for QA

## Notes for Development Team

- **Global Navigation**: Consistent header with logo, menu, and primary CTA button
- **Global Footer**: Consistent footer with contact info, service links, and social media
- **Annotation Toggle**: Ensure this functionality is preserved during Elementor build
- **Mobile-First**: All breakpoints should be tested on actual devices
- **Accessibility**: Ensure all interactive elements have proper focus states and ARIA labels
- **Performance**: Optimize images and minimize CSS/JS for fast loading

## Questions?

Refer to the accompanying documents:
- **Deliverable 1**: Sitemap & Information Architecture
- **Deliverable 2**: ACF & CPT Architecture Plan
- **Deliverable 3**: Critical User Journey Maps
- **Deliverable 4**: SEO & Content Strategy
- **Deliverable 5**: Low-Fidelity Wireframes (this project)
- **Deliverable 6**: Technical Handoff Brief

---

**Project**: Kidmans Partners Website Redesign  
**Created**: May 2026  
**Status**: Ready for Elementor Implementation
