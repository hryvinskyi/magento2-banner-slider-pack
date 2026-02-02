# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.1] - 2026-02-02

### Added
- New Analytics module (`hryvinskyi/magento2-banner-slider-analytics` v1.0.0)

### Analytics Features
- **Statistics Tracking**
  - Impression tracking for banner views
  - Click tracking for banner interactions
  - Automatic CTR (click-through rate) calculation
  - Daily aggregated statistics storage
  - Multi-store support with store view filtering

## [1.0.0] - 2026-01-31

### Added
- Initial release of Banner Slider Pack
- Complete slider management system with four modular components:
  - `hryvinskyi/magento2-banner-slider-api` (v1.0.0) - API interfaces and contracts
  - `hryvinskyi/magento2-banner-slider` (v1.0.0) - Core business logic
  - `hryvinskyi/magento2-banner-slider-admin-ui` (v1.0.0) - Admin interface
  - `hryvinskyi/magento2-banner-slider-frontend-ui` (v1.0.0) - Frontend display

### Features

#### Slider Management
- Create unlimited sliders with unique configurations
- Multi-store support with store view targeting
- Customer group targeting for personalized content
- Date-based scheduling with from/to visibility dates
- Priority-based display ordering

#### Banner Types
- **Image banners** with responsive cropping support
- **Video banners** supporting YouTube, Vimeo, and local files (MP4, WebM)
- **Custom HTML banners** for maximum flexibility
- Link URLs with configurable target (same tab/new tab)
- Alt text and title attributes for accessibility

#### Responsive Image System
- Breakpoint-based image cropping
- Default breakpoints: Desktop (1200px+), Tablet (768-1199px), Mobile (<768px)
- Custom breakpoints per slider
- WebP format generation with quality control
- AVIF format generation with quality control
- Proper `<picture>` element output with source sets

#### Video Support
- YouTube video embedding
- Vimeo video embedding
- Local MP4 video hosting
- Local WebM video hosting
- Background mode (autoplay, muted, loop, no controls)
- Custom aspect ratio configuration

#### Admin Interface
- Grid listings for sliders and banners
- Interactive visual image cropper
- Client-side WebP/AVIF compression using jsquash (WASM)
- Before/after image comparison preview
- Drag-and-drop file uploads
- Video uploader with format validation

#### Frontend Display
- Splide.js carousel integration
- Configurable animation effects (slide, fade, loop)
- Autoplay with customizable interval
- Navigation arrows
- Pagination dots
- Lazy loading support
- Responsive breakpoint configuration

#### Performance Optimizations
- LCP optimization with preload links
- Native lazy loading for images
- N+1 query prevention
- Full Page Cache compatibility
- Proper cache tag management

#### Database Schema
- `hryvinskyi_banner_slider` - Main slider table
- `hryvinskyi_banner_slider_banner` - Banner content table
- `hryvinskyi_banner_slider_image` - Responsive images table
- `hryvinskyi_banner_slider_breakpoint` - Breakpoints table
- `hryvinskyi_banner_slider_responsive_crop` - Crop configurations table

### Requirements
- PHP 8.1+
- Magento 2.4.x
