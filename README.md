
# 🌅 Lumos Theme for Home Assistant

**Lumos** is a modern, elegant, and highly customizable theme for Home Assistant. Inspired by clean and minimalistic design principles, this theme is designed to be visually soothing and functionally versatile, with **light** and **dark** modes optimized for daily use.

---

## 🌟 Features

### 🌓 Light and Dark Modes
- **Light Mode**: 
  - Soft gray backgrounds to reduce glare and eye strain.
  - Adjusted contrast for text and UI elements for a friendlier experience.
  - Subtle shadows on cards for a clean, modern look.
- **Dark Mode**:
  - Balanced dark gray tones for optimal contrast.
  - Enhanced visibility for radio buttons and checkboxes.
  - Blue accents consistent with the theme’s primary color for active elements.

### 🎨 Seasonal Colors
Predefined color palettes for different seasons:
- **Spring**: Fresh greens.
- **Summer**: Warm yellows and oranges.
- **Autumn**: Earthy browns and oranges.
- **Winter**: Cool blues and whites.

### 👓 Accessibility
- Optimized text contrast for better readability.
- Clear differentiation between active and inactive elements.
- Subtle highlights for interactive elements on hover.

### ⚙️ Customizations
- Fully compatible with custom cards, including Mushroom Cards.
- Dynamic colors for primary elements, adjustable to user preferences.
- Mobile-optimized card designs with rounded corners for a polished look.

---

## 🛠️ Installation

1. Clone or download this repository.
2. Copy the `Lumos.yaml` file to your Home Assistant themes folder:
   - Recommended path: `config/themes/lumos.yaml`.
3. Add the following to your `configuration.yaml` file if not already included:

   ```yaml
   frontend:
     themes: !include_dir_merge_named themes
    ```

4.	Restart Home Assistant.
5.	Go to your profile (Profile > Theme) and select Lumos.

### 🌈 Seasonal Automation (Optional)

Want the theme to change dynamically based on the season? Use Home Assistant automations to adjust colors or switch themes.

Example automation for seasons:

   ```yaml
automation:
  - alias: "Change Theme by Season"
    trigger:
      - platform: time
        at: "00:00:00"
    action:
      - choose:
          - conditions:
              - condition: template
                value_template: "{{ now().month in [3, 4, 5] }}"
            sequence:
              - service: frontend.set_theme
                data:
                  name: Lumos
          - conditions:
              - condition: template
                value_template: "{{ now().month in [6, 7, 8] }}"
            sequence:
              - service: frontend.set_theme
                data:
                  name: Lumos
          - conditions:
              - condition: template
                value_template: "{{ now().month in [9, 10, 11] }}"
            sequence:
              - service: frontend.set_theme
                data:
                  name: Lumos
          - conditions:
              - condition: template
                value_template: "{{ now().month in [12, 1, 2] }}"
            sequence:
              - service: frontend.set_theme
                data:
                  name: Lumos
   ```

### 🎛️ User Customization

You can add an input select to allow the user to manually select their preferred season. An automation can then apply the corresponding colors based on the user’s choice.

Example configuration:

   ```yaml
input_select:
  season:
    name: Choose Season
    options:
      - Spring
      - Summer
      - Autumn
      - Winter
    initial: Spring
   ```

### ✨ Conclusion

Lumos offers a beautiful and practical way to enhance your Home Assistant interface. Whether you prefer light, dark, or seasonal themes, this design ensures comfort and clarity.

Feel free to suggest improvements, open an issue, or contribute to the project. Enjoy your Lumos Theme experience! 😊

---

