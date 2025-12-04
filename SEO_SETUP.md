# SEO Setup Documentation

## Overview
This document outlines the SEO implementation for Attic Adult Family Home website.

## ✅ Implemented Features

### 1. Meta Tags & Descriptions
All pages now include:
- **Meta Titles**: Optimized, unique titles for each page (50-60 characters)
- **Meta Descriptions**: Compelling descriptions (150-160 characters) with keywords
- **Meta Keywords**: Relevant local and service-based keywords
- **Canonical URLs**: Prevent duplicate content issues
- **Open Graph Tags**: For better social media sharing (Facebook, LinkedIn)
- **Twitter Card Tags**: Optimized Twitter sharing

### 2. Google Business Profile Connection
- **Schema Markup**: LocalBusiness schema includes `sameAs` field for Google Business Profile
- **Location**: Currently set to placeholder - needs to be updated with actual Google Business CID
- **Setup Instructions**: See comments in HTML files for step-by-step guide

### 3. Local Schema Markup (JSON-LD)
All pages include structured data:

#### Home Page (index.html)
- Complete LocalBusiness schema
- Address, phone, email
- Service offerings catalog
- Aggregate ratings
- Opening hours (24/7)
- Geographic coordinates
- Service area radius

#### About Us Page
- LocalBusiness schema with founder information
- Founding date (2018)
- Company history and mission

#### Services Page
- Detailed service catalog with 8+ services
- Each service includes name and description
- Helps with service-specific search queries

#### Gallery Page
- LocalBusiness schema with image references
- Supports image search optimization

#### Contact Page
- Complete LocalBusiness schema
- ReserveAction schema for tour scheduling
- Full contact information

## 📋 Next Steps

### 1. Update Google Business Profile CID
1. Go to https://business.google.com
2. Create or claim your Google Business Profile
3. After verification, find your CID in the Google Maps URL
4. Replace `YOUR_GOOGLE_BUSINESS_CID` in the schema markup on:
   - `index.html` (line ~75)
   - `contact-us.html` (line ~95)

### 2. Update Image URLs
Replace placeholder image URLs in Open Graph and schema markup:
- `https://www.atticafh.com/images/attic-afh-og-image.jpg`
- `https://www.atticafh.com/images/attic-afh-logo.png`
- `https://www.atticafh.com/images/attic-afh-building.jpg`
- Gallery images in gallery.html schema

### 3. Update Website URL
If your actual domain differs from `https://www.atticafh.com`, update:
- All canonical URLs
- Open Graph URLs
- Schema markup URLs

### 4. Verify Schema Markup
Test your structured data using:
- Google Rich Results Test: https://search.google.com/test/rich-results
- Schema.org Validator: https://validator.schema.org/

### 5. Submit Sitemap
Create and submit a sitemap.xml to:
- Google Search Console
- Bing Webmaster Tools

## 📊 SEO Benefits

### Local SEO
- ✅ Appears in "near me" searches
- ✅ Google Maps integration ready
- ✅ Local business information structured
- ✅ Service area defined

### Search Engine Visibility
- ✅ Unique, keyword-rich titles
- ✅ Compelling meta descriptions
- ✅ Proper heading structure
- ✅ Semantic HTML markup

### Social Media
- ✅ Rich previews on Facebook/LinkedIn
- ✅ Optimized Twitter cards
- ✅ Professional appearance when shared

### Rich Snippets
- ✅ Star ratings display potential
- ✅ Business hours in search results
- ✅ Contact information in search
- ✅ Service listings in search

## 🔍 Keywords Targeted

### Primary Keywords
- Adult family home
- Senior care
- Elderly care
- Dementia care
- Assisted living

### Location-Based Keywords
- Auburn WA
- Auburn senior care
- Adult family home Auburn
- Senior living Auburn
- 29836 113th Way SE

### Service-Specific Keywords
- Memory care
- Medication management
- 24/7 nursing
- Personalized senior care
- Home-like senior facility

## 📝 Notes

- All schema markup follows Schema.org standards
- Meta descriptions are optimized for click-through rates
- Titles include location for local SEO
- Canonical URLs prevent duplicate content penalties
- Mobile-friendly (important for SEO ranking)

