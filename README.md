# README for Django Invoice API

## Project Overview
This Django project provides a RESTful API for managing invoices and their details. It includes models for `Invoice` and `InvoiceDetail`, with nested serializers for handling data, and a view that supports creating and updating invoices along with their details in a single API call.

## Features
- Create a new invoice with multiple details.
- Update an existing invoice and replace its details with new ones provided in the payload.
- Nested serializers for handling detailed data validation.

## Prerequisites
- Python 3.x
- Django 4.x
- Django REST Framework

## Setup Instructions
1. **Clone the repository:**
   ```bash
   git clone <repository-url>
   cd <repository-directory>
   ```

2. **Create and activate a virtual environment:**
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install the required packages:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Run database migrations:**
   ```bash
   python manage.py migrate
   ```

5. **Start the development server:**
   ```bash
   python manage.py runserver
   ```

6. **Access the API endpoint:**
   Navigate to `http://127.0.0.1:8000/api/invoices/` for creating and updating invoices.

## Example Payload
### Create or Update Invoice
```json
{
  "invoice_number": "INV001",
  "customer_name": "John Doe",
  "date": "2024-11-12",
  "details": [
    {
      "description": "Product A",
      "quantity": 2,
      "price": 50.00,
      "line_total": 100.00
    },
    {
      "description": "Product B",
      "quantity": 1,
      "price": 75.00,
      "line_total": 75.00
    }
  ]
}
```

## Assumptions Made
- The `line_total` field is provided in the payload and is assumed to be calculated on the client side.
- All invoice numbers are unique.

## Deployment Notes
To deploy the application, you can use a platform like Heroku, Vercel, or DigitalOcean. Ensure the following:
- Update `ALLOWED_HOSTS` in `settings.py`.
- Configure a production-level database (e.g., PostgreSQL).

## License
This project is licensed under the MIT License.

## Contact
For any questions, please contact [milanbiranwar29@gmail.com].
