# Magento 2 & Adobe Commerce Banner Slider

Complete banner slider solution with responsive images, video support, WebP/AVIF optimization, and advanced cropping tools.

## Overview

This metapackage provides a complete solution for managing banner sliders in Magento 2. It includes powerful features for creating responsive image banners, video banners (YouTube, Vimeo, local), and custom HTML content with a modern Splide.js carousel.

## Included Packages

### Core Modules
- **hryvinskyi/magento2-banner-slider-api** (v1.0.0) - API interfaces and contracts
- **hryvinskyi/magento2-banner-slider** (v1.0.0) - Core business logic and data layer
- **hryvinskyi/magento2-banner-slider-admin-ui** (v1.0.0) - Admin panel interface with responsive cropper
- **hryvinskyi/magento2-banner-slider-frontend-ui** (v1.0.0) - Frontend display with Splide.js carousel

## Key Features

### Banner Types
- **Image Banners** - Static images with responsive variants for all breakpoints
- **Video Banners** - YouTube, Vimeo, or local video files (MP4, WebM)
- **Custom HTML** - Full HTML content support for maximum flexibility

### Responsive Images
- **Breakpoint-based cropping** - Different crops for desktop, tablet, and mobile
- **WebP generation** - Automatic WebP conversion for smaller file sizes
- **AVIF generation** - Next-gen format support for maximum compression
- **Picture element** - Proper `<picture>` with source sets and fallbacks

### Video Support
- **YouTube** - Embed YouTube videos with custom options
- **Vimeo** - Embed Vimeo videos with custom options
- **Local MP4/WebM** - Self-hosted video files with native `<video>` element
- **Background mode** - Videos as backgrounds (autoplay, muted, loop, no controls)
- **Custom aspect ratios** - Configure video aspect ratios per banner

### Admin Features
- **Visual cropper** - Interactive image cropping interface
- **Client-side compression** - WebP/AVIF compression in browser using jsquash
- **Before/after preview** - Compare original vs compressed images
- **Drag-and-drop uploads** - Easy image and video uploading
- **Multi-store support** - Target sliders to specific store views
- **Customer group targeting** - Show sliders to specific customer groups
- **Date scheduling** - Schedule slider visibility with from/to dates

### Carousel Features (Splide.js)
- **Multiple slide types** - Loop, slide, fade effects
- **Autoplay** - Configurable auto-advance with customizable interval
- **Navigation** - Previous/next arrows with styling options
- **Pagination** - Dot indicators with styling options
- **Lazy loading** - Native lazy loading for better performance
- **Responsive breakpoints** - Different settings per viewport

### Performance
- **Preload links** - Generate `<link rel="preload">` for LCP images
- **Lazy loading** - Native `loading="lazy"` for below-fold images
- **N+1 prevention** - Efficient queries with preloaded responsive crops
- **Full Page Cache** - Proper cache tags for FPC compatibility

## Installation

```bash
composer require hryvinskyi/magento2-banner-slider-pack
php bin/magento module:enable Hryvinskyi_BannerSliderApi Hryvinskyi_BannerSlider Hryvinskyi_BannerSliderAdminUi Hryvinskyi_BannerSliderFrontendUi
php bin/magento setup:upgrade
php bin/magento setup:di:compile
php bin/magento cache:flush
```

## Configuration

### Creating a Slider

1. Navigate to **Content > Banner Slider > Sliders**
2. Click **Add New Slider**
3. Configure slider settings:
   - **Name** - Identifier for the slider
   - **Status** - Enable/disable
   - **Store Views** - Target store views
   - **Customer Groups** - Target customer groups
   - **Animation** - Effect type, auto width/height, loop
   - **Autoplay** - Enable and set interval
   - **Navigation** - Arrows and pagination
   - **Responsive** - Items per breakpoint

### Adding Banners

1. Navigate to **Content > Banner Slider > Banners**
2. Click **Add New Banner**
3. Select parent slider
4. Choose banner type (Image, Video, or Custom HTML)
5. Configure content:
   - **Image** - Upload desktop image, configure responsive crops
   - **Video** - Enter URL or upload local file
   - **Custom HTML** - Enter HTML content
6. Set link URL and target
7. Configure position and date range

### Responsive Image Cropping

1. Edit a banner
2. In the Responsive Crops section, click on a breakpoint
3. Use the visual cropper to adjust the crop area
4. Enable WebP/AVIF generation and set quality
5. Save the banner

### Placing the Slider

#### Widget in CMS Page/Block
```
{{widget type="Hryvinskyi\BannerSliderFrontendUi\Block\Widget\Slider" slider_id="1" template="Hryvinskyi_BannerSliderFrontendUi::slider.phtml"}}
```

#### Layout XML
```xml
<referenceContainer name="content">
    <block class="Hryvinskyi\BannerSliderFrontendUi\Block\Widget\Slider" name="banner.slider">
        <arguments>
            <argument name="slider_id" xsi:type="number">1</argument>
        </arguments>
    </block>
</referenceContainer>
```

## Database Schema

| Table | Description |
|-------|-------------|
| `hryvinskyi_banner_slider` | Slider configuration |
| `hryvinskyi_banner_slider_banner` | Banner content |
| `hryvinskyi_banner_slider_image` | Responsive image variants |
| `hryvinskyi_banner_slider_breakpoint` | Viewport breakpoints |
| `hryvinskyi_banner_slider_responsive_crop` | Crop configurations |

## Requirements

- PHP 8.1, 8.2, or 8.3
- Magento 2.4.x
- Composer

## Dependencies

The pack requires these additional packages (installed automatically):
- hryvinskyi/magento2-base
- hryvinskyi/magento2-splide-js
- hryvinskyi/magento2-head-tag-manager
- hryvinskyi/image-binaries
- symfony/process

## Support

- Report issues: https://github.com/hryvinskyi/magento2-banner-slider-pack/issues
- Email: volodymyr@hryvinskyi.com

## Author

**Volodymyr Hryvinskyi**
- Email: volodymyr@hryvinskyi.com
- Website: https://hryvinskyi.com

## License

MIT License - see LICENSE file for details

## Changelog

See [CHANGELOG.md](CHANGELOG.md) for detailed version history.
