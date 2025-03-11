# 🌱 NDVI-Based Crop Yield Prediction System 🌾

Welcome to the **NDVI-Based Crop Yield Prediction System**! This project is designed to help farmers and agricultural experts predict crop yields using satellite imagery and NDVI (Normalized Difference Vegetation Index) values. The system allows users to upload satellite images, visualize NDVI trends, select prediction models, and download results in CSV or JSON format.

---

## 🚀 **Features**

- **Upload Satellite Images** 📤: Upload GeoTIFF format images for a specific field or cell.
- **Visualize NDVI Values** 📊: View NDVI trends over time using interactive charts.
- **Select Prediction Models** 🤖: Choose from Linear Regression, Decision Tree, or Random Forest models.
- **Input Additional Parameters** 🌦️: Add weather data, soil type, and other parameters for accurate predictions.
- **Real-Time Yield Predictions** ⏱️: Get instant yield predictions based on NDVI trends.
- **Download Results** 📥: Export results in CSV or JSON format for further analysis.

---

## 🛠️ **Tech Stack**

- **Backend**: Go (using [Fiber](https://gofiber.io/))
- **Frontend**: Plain HTML, CSS, and JavaScript
- **Charting Library**: [Chart.js](https://www.chartjs.org/)
- **File Handling**: GeoTIFF processing and CSV/JSON generation

---

## 📂 **File Structure**

Here’s a detailed breakdown of the project structure and the role of each file:

```
ndvi-yield-prediction/
├── cmd/
│   └── server/
│       └── main.go                 # Entry point for the Go application
├── internal/
│   ├── api/
│   │   ├── handlers/               # API handlers for different functionalities
│   │   │   ├── image_handler.go    # Handles image upload and processing
│   │   │   ├── ndvi_handler.go     # Retrieves NDVI values for visualization
│   │   │   ├── prediction_handler.go # Handles yield prediction requests
│   │   │   └── download_handler.go # Manages file downloads (CSV/JSON)
│   │   ├── middleware/             # Middleware for authentication (if needed)
│   │   │   └── auth.go
│   │   └── router.go               # Defines API routes
│   ├── models/                     # Data models for fields, images, NDVI, and predictions
│   │   ├── field.go
│   │   ├── image.go
│   │   ├── ndvi.go
│   │   └── prediction.go
│   ├── services/                   # Business logic for image processing, NDVI calculation, and predictions
│   │   ├── image_service.go        # Processes uploaded images
│   │   ├── ndvi_service.go         # Calculates NDVI values
│   │   └── prediction_service.go  # Predicts crop yield using selected models
│   └── utils/                      # Utility functions for file handling and NDVI calculations
│       ├── geotiff.go              # Handles GeoTIFF file processing
│       ├── ndvi_calculator.go      # Calculates NDVI from satellite images
│       └── file_handler.go         # Manages file downloads and storage
├── static/
│   ├── css/                        # CSS files for styling the UI
│   │   ├── main.css                # Main styles for the application
│   │   ├── components.css          # Styles for reusable components
│   │   └── responsive.css          # Responsive design for mobile-friendly layout
│   ├── js/                         # JavaScript files for frontend functionality
│   │   ├── main.js                 # Handles form submissions and basic interactions
│   │   ├── ndvi_visualization.js   # Renders NDVI charts using Chart.js
│   │   ├── map.js                  # (Optional) For displaying maps (if implemented)
│   │   ├── prediction.js           # Handles prediction model selection and input
│   │   └── api.js                  # Utility functions for API calls
│   └── img/                        # Static images (e.g., logos)
│       └── logo.svg
├── templates/                      # HTML templates for the frontend
│   ├── index.html                  # Landing page
│   ├── dashboard.html              # Dashboard for NDVI visualization and predictions
│   ├── upload.html                 # Page for uploading satellite images
│   └── prediction.html             # Page for yield prediction and model selection
├── go.mod                          # Go module file for dependency management
├── go.sum                          # Go checksum file for dependencies
└── README.md                       # Project documentation (you're here!)
```

---

## 🧩 **File Roles**

### **Backend**

1. **`cmd/server/main.go`**:
   - Entry point for the application.
   - Initializes the Fiber server and serves static files.
   - Sets up HTML templates and API routes.

2. **`internal/api/router.go`**:
   - Defines all API routes for the application.
   - Routes include image upload, NDVI retrieval, yield prediction, and file downloads.

3. **`internal/api/handlers/`**:
   - Contains handlers for processing API requests:
     - **`image_handler.go`**: Handles image upload and processing.
     - **`ndvi_handler.go`**: Retrieves NDVI values for visualization.
     - **`prediction_handler.go`**: Processes yield prediction requests.
     - **`download_handler.go`**: Manages file downloads (CSV/JSON).

4. **`internal/models/`**:
   - Defines data models for fields, images, NDVI values, and predictions.

5. **`internal/services/`**:
   - Implements business logic:
     - **`image_service.go`**: Processes uploaded satellite images.
     - **`ndvi_service.go`**: Calculates NDVI values from images.
     - **`prediction_service.go`**: Predicts crop yield using selected models.

6. **`internal/utils/`**:
   - Utility functions for:
     - **`geotiff.go`**: GeoTIFF file processing.
     - **`ndvi_calculator.go`**: NDVI calculation.
     - **`file_handler.go`**: File download and storage.

---

### **Frontend**

1. **`templates/`**:
   - HTML templates for the UI:
     - **`index.html`**: Landing page with links to upload and dashboard.
     - **`upload.html`**: Page for uploading satellite images.
     - **`dashboard.html`**: Displays NDVI charts and predictions.
     - **`prediction.html`**: Page for selecting models and inputting parameters.

2. **`static/css/`**:
   - CSS files for styling:
     - **`main.css`**: Global styles.
     - **`components.css`**: Reusable component styles.
     - **`responsive.css`**: Ensures mobile-friendly layout.

3. **`static/js/`**:
   - JavaScript files for interactivity:
     - **`main.js`**: Handles form submissions and basic interactions.
     - **`ndvi_visualization.js`**: Renders NDVI charts using Chart.js.
     - **`prediction.js`**: Handles prediction model selection and input.
     - **`api.js`**: Utility functions for making API calls.

4. **`static/img/`**:
   - Static images (e.g., logos).

---

## 🖥️ **How to Run the Project**

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/ndvi-yield-prediction.git
   cd ndvi-yield-prediction
   ```

2. Install dependencies:
   ```bash
   go mod tidy
   ```

3. Start the server:
   ```bash
   go run cmd/server/main.go
   ```

4. Open your browser and navigate to:
   ```
   http://localhost:3000
   ```

---

## 📝 **Future Enhancements**

- Add user authentication and authorization.
- Integrate a map for field selection.
- Support more prediction models (e.g., Neural Networks).
- Improve error handling and user feedback.
- Add unit tests for backend services.

---

## 🙏 **Contributing**

Contributions are welcome! Please open an issue or submit a pull request for any improvements or bug fixes.

---

## 📄 **License**

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

Happy farming! 🌾🚜
