# Brandify - WordPress Admin Customization Plugin

Complete WordPress admin customization with white labeling, menu editor, login customizer, dark mode, security features, and Elementor-powered dashboard widgets and admin pages.

## Features

### 🎨 White Labeling
- Custom admin and login logos
- Color scheme customization
- **Google Fonts integration** with 1800+ popular fonts
- **Background customization** (solid colors, gradients, or images)
- Custom admin footer text
- Remove WordPress branding

### 📋 Admin Menu Editor
- Drag-and-drop menu reordering
- Show/hide menu items
- Rename menu items
- Change menu icons
- Role-based menu visibility
- Export/import menu configurations

### 🔐 Login Customizer
- Custom login page backgrounds
- Logo upload and customization
- Form styling (colors, borders, shadows)
- Custom redirect after login (role-based)
- Custom CSS support

### 🌙 Dark Mode
- Toggle dark mode from admin bar
- Auto-scheduling (time-based)
- System preference detection
- Per-user preferences
- Smooth transition animations

### 🔒 Security Features
- Custom login URL
- Hide WordPress version
- Disable XML-RPC
- Hide admin notices
- Activity logging
- Admin bar visibility control

### 🎯 Elementor Integration (Unique Feature)
- Create dashboard widgets with Elementor
- Build custom admin pages visually
- No coding required
- Full Elementor widget support
- Pre-built widget templates:
  - Quick Links Widget
  - Stats Widget
  - Activity Log Widget

## Requirements

- WordPress 6.0 or higher
- PHP 7.4 or higher
- Elementor (optional, only for Elementor integration features)

## Installation

1. Upload the `brandify` folder to `/wp-content/plugins/`
2. Activate the plugin through the 'Plugins' menu in WordPress
3. Navigate to **Brandify** in the admin menu
4. Configure your desired settings

### ⚠️ Important: Elementor Integration Setup

To use Elementor features (Dashboard Widgets & Admin Pages):

1. Install and activate Elementor (free version works)
2. Go to **Elementor → Settings → General**
3. Scroll to "Post Types" and enable **"Admin Pages"** and **"Dashboard Widgets"**
4. Click **"Save Changes"**
5. Now you can create and edit with Elementor!

**Without this step, you won't be able to edit widgets/pages with Elementor!**

## Usage

### White Labeling

1. Go to **Brandify > White Labeling**
2. Upload your logos
3. Choose colors for your admin interface
4. Select Google Fonts for typography
5. Customize the background (color, gradient, or image)
6. Save changes

### Menu Editor

1. Go to **Brandify > Menu Editor**
2. Enable the menu editor
3. Drag and drop menu items to reorder
4. Use the action buttons to hide, rename, or change icons
5. Save your menu configuration

### Login Customizer

1. Go to **Brandify > Login Customizer**
2. Enable login customization
3. Upload a logo
4. Set background color or image
5. Customize form styling
6. Save changes

### Dark Mode

1. Go to **Brandify > Dark Mode**
2. Enable dark mode
3. Configure auto-scheduling if desired
4. Users can toggle dark mode from the admin bar

### Security

1. Go to **Brandify > Security**
2. Set a custom login URL (optional but recommended)
3. Enable additional security features
4. Configure activity logging
5. Save changes

### Elementor Integration

**⚠️ First-time setup:** Make sure you've enabled the Brandify post types in Elementor settings (see Installation section above)!

1. Install and activate Elementor (if not already installed)
2. Enable "Admin Pages" and "Dashboard Widgets" in Elementor → Settings → General → Post Types
3. Go to **Brandify → Elementor**
4. Create a new dashboard widget or admin page
5. Click "Edit with Elementor"
6. Design your widget/page using Elementor
7. Publish - your widget appears on the dashboard or your page appears in the admin menu!

## File Structure

```
brandify/
├── brandify.php (Main plugin file)
├── includes/
│   ├── class-brandify.php (Core plugin class)
│   ├── class-brandify-activator.php
│   ├── class-brandify-deactivator.php
│   ├── class-brandify-loader.php
│   ├── modules/
│   │   ├── class-white-labeling.php
│   │   ├── class-admin-menu-editor.php
│   │   ├── class-login-customizer.php
│   │   ├── class-dark-mode.php
│   │   ├── class-security.php
│   │   └── class-elementor-integration.php
│   └── admin/
│       ├── class-brandify-admin.php
│       ├── class-brandify-settings.php
│       └── views/ (Settings page templates)
├── assets/
│   ├── css/ (Stylesheets)
│   ├── js/ (JavaScript files)
│   └── images/
├── elementor/
│   └── widgets/ (Custom Elementor widgets)
└── languages/ (Translation files)
```

## Developer Notes

### Hooks and Filters

Brandify provides several hooks for developers:

```php
// Customize available Google Fonts
add_filter('brandify_google_fonts', function($fonts) {
    $fonts['Your Font'] = 'Your Font';
    return $fonts;
});

// Modify white labeling settings
add_filter('brandify_white_label_settings', function($settings) {
    // Modify settings
    return $settings;
});
```

### Custom Elementor Widgets

To create custom Elementor widgets for Brandify:

```php
class Your_Custom_Widget extends \Elementor\Widget_Base {
    public function get_name() {
        return 'your-widget-name';
    }
    
    public function get_categories() {
        return array('brandify');
    }
    
    // Additional widget methods...
}
```

## Security

- All user inputs are sanitized and validated
- Nonces are used for all AJAX requests
- Capability checks are performed before saving settings
- SQL queries use prepared statements
- Activity logging tracks important actions

## Performance

- Minimal database queries
- Assets are only loaded on admin pages
- CSS/JS files are minified
- Google Fonts are loaded asynchronously

## Compatibility

Tested with:
- WordPress 6.0 - 6.4
- PHP 7.4 - 8.2
- Elementor 3.0+
- Most popular WordPress themes and plugins

## FAQ

**Q: Can I use Brandify without Elementor?**
A: Yes! All features work independently. Elementor is only required for the Dashboard Widgets and Custom Admin Pages features.

**Q: Will my customizations persist after plugin updates?**
A: Yes, all settings are stored in the WordPress database and remain intact through updates.

**Q: Can I export/import settings between sites?**
A: The Menu Editor supports export/import. For other features, you can use WordPress export tools or manually transfer settings via the database.

**Q: Is Brandify compatible with multisite?**
A: Yes, Brandify works on WordPress multisite installations.

**Q: Does dark mode work with all themes/plugins?**
A: Dark mode applies comprehensive styling to the WordPress admin area. Some third-party plugins with custom styling may need additional CSS adjustments.

## Support

For bug reports, feature requests, or support:
- GitHub: https://github.com/cursorwp/brandify
- Documentation: See **Brandify > Documentation** in your WordPress admin

## License

This plugin is licensed under the GPL v2 or later.

## Credits

- Google Fonts - https://fonts.google.com/
- Elementor - https://elementor.com/
- WordPress Color Picker
- jQuery UI Sortable

## Changelog

### Version 1.0.0 (Initial Release)
- White Labeling with Google Fonts and background customization
- Admin Menu Editor with drag-and-drop
- Login Customizer
- Dark Mode with auto-scheduling
- Security features
- Elementor integration for dashboard widgets and admin pages

---

Made with ❤️ by the CursorWP Team

