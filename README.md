# Laravel Dynamic Form Builder


A powerful and flexible form builder system built with Laravel, allowing users to create, manage, and collect submissions for dynamic forms through a drag-and-drop interface.

## 🚀 Features

- **Dynamic Form Creation**: Drag-and-drop form builder interface
- **Form Management**: Create, view, and manage multiple forms
- **Form Submissions**: Collect and store form submissions
- **Submission Management**: View and manage form responses
- **Responsive Design**: Bootstrap-based responsive layout
- **Real-time Preview**: Live form preview while building

## 📋 Requirements

- PHP >= 7.4
- Laravel >= 8.x
- MySQL/PostgreSQL
- Composer
- Node.js & NPM (for asset compilation)

## 🛠️ Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/laravel-dynamic-form-builder.git
```

2. Install PHP dependencies:
```bash
composer install
```

3. Copy environment file:
```bash
cp .env.example .env
```

4. Generate application key:
```bash
php artisan key:generate
```

5. Configure your database in `.env`:
```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=your_database
DB_USERNAME=your_username
DB_PASSWORD=your_password
```

6. Run migrations:
```bash
php artisan migrate
```

## 📚 Project Structure

```
├── app
│   ├── Http
│   │   ├── Controllers
│   │   │   ├── FormController.php
│   │   │   └── FormSubmissionController.php
│   ├── Models
│   │   ├── Form.php
│   │   └── FormSubmission.php
├── database
│   └── migrations
│       ├── create_forms_table.php
│       └── create_form_submissions_table.php
├── resources
│   └── views
│       └── forms
│           ├── create.blade.php
│           ├── index.blade.php
│           ├── show.blade.php
│           └── submissions.blade.php
└── routes
    └── web.php
```

## 💻 Usage

### Creating a New Form

1. Navigate to `/forms/create`
2. Enter form title
3. Use drag-and-drop interface to add fields
4. Configure field properties
5. Click "Save Form"

### Managing Forms

- View all forms at `/forms`
- Click "Fill Form" to view and submit a form
- Click "View Submissions" to see form responses

### Collecting Submissions

- Share the form URL with users
- Users can fill and submit the form
- View submissions in the admin dashboard

## 🔌 Dependencies

### PHP Packages
```json
{
    "php": "^7.4|^8.0",
    "laravel/framework": "^8.0"
}
```

### JavaScript Libraries
```html
<!-- jQuery and UI -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jqueryui/1.12.1/jquery-ui.min.js"></script>

<!-- Form Builder -->
<script src="https://formbuilder.online/assets/js/form-builder.min.js"></script>
<script src="https://formbuilder.online/assets/js/form-render.min.js"></script>
```

### CSS
```html
<!-- Bootstrap -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css">
```

## 🗄️ Database Structure

### Forms Table
```php
Schema::create('forms', function (Blueprint $table) {
    $table->id();
    $table->string('title');
    $table->json('form_data');
    $table->timestamps();
});
```

### Form Submissions Table
```php
Schema::create('form_submissions', function (Blueprint $table) {
    $table->id();
    $table->foreignId('form_id')->constrained('forms')->onDelete('cascade');
    $table->json('submission_data');
    $table->timestamps();
});
```

## 🔒 Security

- Form submissions are validated server-side
- CSRF protection enabled
- SQL injection prevention through Laravel's query builder
- XSS protection through Laravel's built-in security features

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.

## 👨‍💻 Author

Your Name - [@dev-sync-laravel](https://github.com/dev-sync-laravel)

## 🙏 Acknowledgments

- [Laravel](https://laravel.com) - The web framework used
- [jQuery FormBuilder](https://formbuilder.online) - Form builder plugin
- [Bootstrap](https://getbootstrap.com) - Frontend framework

## 📞 Support

For support, email info@devsync.com or create an issue in this repository.
