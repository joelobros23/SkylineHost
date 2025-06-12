# Project Plan: SkylineHost

**Description:** A user-friendly web hosting platform built on Ruby on Rails, offering domain management and basic hosting features.


## Development Goals

- [ ] Configure tailwindcss-rails by running `rails tailwindcss:install` and updating `app/assets/stylesheets/application.tailwind.css` with basic styling.
- [ ] Implement model validations in `app/models/domain.rb` to ensure that `name`, `plan`, and `user_id` are present and that `name` is a valid domain format using a custom validator.
- [ ] Customize the Domain scaffold views (e.g., `index.html.erb`, `show.html.erb`, `_form.html.erb`) to utilize Tailwind CSS classes for enhanced UI, focusing on consistent spacing, typography, and color palettes.
- [ ] Modify the `DomainsController` to associate new domains with the currently logged-in user.  Before creating a new domain, assign `current_user.id` to the domain's `user_id` attribute.  Restrict domain access to only the logged-in user. Ensure users can only view, edit, or delete their own domains.
- [ ] Create a dashboard controller and view (`app/controllers/dashboard_controller.rb` and `app/views/dashboard/index.html.erb`) to display a summary of the user's domains. Include a link to manage domains.
- [ ] Add a `before_action :authenticate_user!` to the `DomainsController` to ensure only authenticated users can access domain management features.
- [ ] Implement a basic pricing plan selection during domain creation. The 'plan' attribute should be limited to predefined options (e.g., 'Basic', 'Standard', 'Premium').
- [ ] Create a custom validator in `app/validators/domain_validator.rb` that checks if a domain name is valid using regex. The validator should check if the provided name matches a simplified domain structure e.g., `[a-z0-9]+.[a-z]{2,3}`.
- [ ] Implement a status update feature for domains (e.g., 'Active', 'Inactive', 'Suspended') using Rails' enum feature in the `Domain` model.
- [ ] Add a 'Last Updated' timestamp to the domain show page, displaying the last time the domain record was modified.
