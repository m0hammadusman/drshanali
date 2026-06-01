# Build Scripts Archive

This folder contains deprecated and archived build/utility scripts that were used during website development and maintenance.

## Archived Scripts

### Image Processing Scripts
- **generate_pub_images.py** - Initial version for generating publication images
- **generate_pub_images_v2.py** - Improved version (superseded by v3)
- **process_assets_v2.py** - Old asset processing script (superseded by v1)

### Navigation/HTML Manipulation
- **add_gallery_nav_v2.py** - Gallery navigation script v2 (superseded by main version)

## Active Scripts

For active build and utility scripts, refer to the root directory. Current active scripts include:
- `add_courses_nav.py` - Add course navigation
- `add_gallery_nav.py` - Add gallery navigation
- `add_loader.py` - Add page loader
- `create_courses.py` - Create course pages
- `generate_pub_images_v3.py` - Current image generation (latest)
- `process_assets.py` - Asset processing (current version)
- `migrate.py` - Content migration
- `inject_seo.py` - SEO injection
- And others...

## Usage

These archived scripts were used during development. If you need to use them:
1. Copy the script from this archive to the root directory
2. Update any hardcoded paths to point to the correct directories
3. Test thoroughly before running on production files

## Removing Duplicates

To clean up the root directory further:
- Verify which versions are truly active before deleting
- Some scripts may have subtle differences worth preserving
- Consider consolidating similar functionality into a single, well-documented script

## Documentation

For details about what each script does, see:
- `DEPLOYMENT.md` - Build and deployment procedures
- `README.md` - Project structure and setup

Last Updated: June 1, 2026
