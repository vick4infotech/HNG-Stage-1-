# Number Classification API

A simple Flask-based API that classifies numbers based on their properties, such as being prime, perfect, armstrong, even, or odd. It also provides a fun fact about the number.

## Features
- Classifies numbers as **prime, perfect, armstrong, even, or odd**
- Returns the **sum of digits** of the number
- Fetches a **fun fact** about the number using an external API

## API Endpoints

### 1. **Classify a Number**
**Endpoint:** `/api/classify-number`

**Method:** `GET`

**Query Parameters:**
- `number` (integer) - The number to classify

**Example Request:**
```sh
GET http://your-ec2-ip:5000/api/classify-number?number=371
```

**Example Response:**
```json
{
  "number": 371,
  "is_prime": false,
  "is_perfect": false,
  "properties": ["armstrong", "odd"],
  "digit_sum": 11,
  "fun_fact": "371 is the sum of three consecutive primes: 113, 127, and 131."
}
```

## Installation & Setup

### 1. **Clone the Repository**
```sh
git clone https://github.com/yourusername/number-api.git
cd number-api
```

### 2. **Install Dependencies**
```sh
pip install flask requests flask-cors
```

### 3. **Run the API Locally**
```sh
python app.py
```

API will be available at: `http://127.0.0.1:5000/api/classify-number?number=371`

## Deployment (AWS EC2)

### **Steps to Deploy:**
1. Launch an **Ubuntu EC2 instance**
2. SSH into the instance:
   ```sh
   ssh -i your-key.pem ubuntu@your-ec2-ip
   ```
3. Install dependencies:
   ```sh
   sudo apt update && sudo apt install python3 python3-pip -y
   pip3 install flask requests flask-cors
   ```
4. Transfer `app.py` to the server (or create it manually)
5. Run the API:
   ```sh
   nohup python3 app.py &
   ```
6. Allow port **5000** in AWS Security Group settings
7. Access API via:
   ```sh
   http://your-ec2-ip:5000/api/classify-number?number=371
   ```

## Future Improvements
- Add support for negative numbers
- Implement caching for fun fact retrieval
- Deploy using Docker and Kubernetes

## License
MIT License
