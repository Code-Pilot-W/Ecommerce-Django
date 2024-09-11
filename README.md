# Django E-commerce Application

This project is a basic e-commerce application built with Django, featuring models for product categories and products. It allows the creation of categories and products, with options to manage availability, stock, and price. The app supports listing products by category and individual product details.

## Features

- **Category Management**: Create, update, and list product categories.
- **Product Management**: Add, update, and delete products with fields for name, description, price, stock, and availability.
- **Image Upload**: Upload product images, with images organized by the date of upload.
- **URL Management**: Each category and product has its unique URL for easy access and SEO optimization.

## Models

### Category Model

Represents a category for organizing products.

- **Fields**:
  - `name`: The name of the category.
  - `slug`: A URL-friendly version of the category name.
  - `created_at`: The timestamp when the category was created.
  - `updated_at`: The timestamp when the category was last updated.

- **Methods**:
  - `get_absolute_url()`: Returns the URL for listing products under the category.

- **Meta Options**:
  - `ordering`: Orders categories alphabetically by name.
  - `verbose_name`: Human-readable singular name for the model.
  - `verbose_name_plural`: Human-readable plural name for the model.

### Product Model

Represents a product in the e-commerce application.

- **Fields**:
  - `category`: ForeignKey to the `Category` model.
  - `name`: The name of the product.
  - `slug`: A URL-friendly version of the product name.
  - `description`: A brief description of the product.
  - `price`: The price of the product.
  - `available`: Boolean indicating if the product is available for purchase.
  - `stock`: Number of items in stock.
  - `created_at`: The timestamp when the product was created.
  - `updated_at`: The timestamp when the product was last updated.
  - `image`: Optional image field for uploading product images.

- **Methods**:
  - `get_absolute_url()`: Returns the URL for the product details page.

- **Meta Options**:
  - `ordering`: Orders products alphabetically by name.
  - `index_together`: Creates a database index on `id` and `slug` for faster lookups.

## How to Run the Application

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/django-ecommerce.git
   cd django-ecommerce
   ```

2. **Install Dependencies**:
   Ensure you have a Python virtual environment activated and install required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. **Apply Migrations**:
   Create the necessary database tables:
   ```bash
   python manage.py migrate
   ```

4. **Run the Development Server**:
   Start the Django development server:
   ```bash
   python manage.py runserver
   ```
   The application will be available at `http://127.0.0.1:8000`.

## App Structure

- **shop/models.py**: Contains the `Category` and `Product` models.
- **shop/apps.py**: Django application configuration for the shop app.
- **manage.py**: Django management script for running commands like migrations and the development server.

## Further Configuration

- **Image Storage**: Ensure the `MEDIA_URL` and `MEDIA_ROOT` settings are configured in your `settings.py` for managing uploaded images.
- **Static Files**: Configure `STATIC_URL` and `STATIC_ROOT` for handling static assets like CSS and JavaScript.

---

This project provides a foundation for building an e-commerce site. You can extend it with additional features like shopping cart functionality, user authentication, and payment gateways.
