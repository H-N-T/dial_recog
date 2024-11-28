# Dial-Based Video Analysis Pipeline

This Python script processes video data to analyze dial measurements, extract segment-based data, and generate outputs such as annotated frames, Excel reports, and visual plots. The pipeline includes interactive steps to configure dial segments and supports customizable frame processing.

---

## **Key Features**
- **Interactive Configuration**: Allows users to define dial center, radius, and segment configuration through mouse clicks.
- **Segment Detection**: Extracts and processes data from specified dial segments in video frames.
- **Data Export**: Saves processed results as Excel files, including individual dial data and combined summaries.
- **Visualization**: Generates interactive HTML plots for individual dials and replicate groups with error bars.
- **Dynamic Thresholding**: Implements adaptive binary thresholding for accurate segment detection.
- **Color Filtering**: Removes specified color ranges (e.g., red to orange) to enhance processing accuracy.

---

## **Modules and Functions**
### 1. **Video Processing**
Processes individual video files to extract dial segment data:
- Removes specified colors (e.g., red-to-orange range).
- Dynamically thresholds grayscale images to enhance segmentation.
- Detects and flags segments based on non-zero pixel counts.

### 2. **Dial Configuration**
Supports manual or pre-configured dial setup:
- Interactive selection of dial center and radius using mouse clicks.
- Maps values to segments based on angular positions.

### 3. **Data Management**
- Saves results for each video in an Excel file, with individual sheets for each dial.
- Combines data from all videos into a single output file with summary statistics.
- Supports replicate groups for averaging and standard deviation calculations.

### 4. **Visualization**
- Plots detected numbers for each dial in interactive graphs.
- Creates error-bar plots for replicate group means with standard deviations.

---

## **Setup and Usage**
### **Dependencies**
Ensure the following Python libraries are installed:
- opencv-python
- numpy
- pandas
- plotly
- json
- math
- os

Install them using pip.

### **Inputs**
- **Video Paths**: Provide paths to video files (separated by spaces).
- **Output Directory**: Specify the base directory for saving outputs.
- **Frame Skip**: Number of frames to skip between processing (default: 60).
- **Segment Threshold**: Threshold for detecting segments (default: 0.2).
- **Frame Range**: Optionally specify start and end frame numbers.

### **Execution**
Run the script in the terminal or an IDE by providing the necessary inputs.

### **Interactive Steps**
1. **Configure Dials**:
   - Select the center and radius using mouse clicks on the displayed frame.
   - Specify the origin and maximum values for the dial to map segment values.

2. **Process Videos**:
   - Automatically process frames based on the configuration, skipping frames as specified.
   - Optionally save processed images for further inspection.

3. **Generate Outputs**:
   - Save combined Excel files with all processed data and summary statistics.
   - Generate interactive HTML plots for visualization.

---

## **Outputs**
### 1. **Processed Frames**
- Annotated images showing detected segments and values, saved as PNG files (optional).

### 2. **Excel Files**
- Individual Excel files for each video, with separate sheets for each dial's data.
- A combined Excel file consolidating all processed videos, including replicate group summaries.

### 3. **Plots**
- Interactive plots for individual dials in each video.
- Combined plots with replicate group means and standard deviations, saved as HTML files.

---

## **Configuration**
The script supports saving and loading configurations to streamline repeated analyses. These configurations include:
- **Dial centers and radii**
- **Segment mapping details**
- **Angular ranges and corresponding values**

Configuration files are stored in JSON format and can be reused across analyses.

---

## **Known Issues and Limitations**
- **Interactive Input**: Dial configuration requires manual interaction through mouse clicks.
- **Processing Speed**: Can be slow for high-resolution videos or extensive frame ranges.
- **Threshold Oscillation**: Adaptive thresholding may oscillate in certain scenarios, though checks mitigate this.

---

## **Future Improvements**
- Automate dial configuration using computer vision or machine learning techniques.
- Enhance thresholding methods to improve processing speed and reliability.
- Add more advanced visualization features for better insights into the data.

---

## **Saving and Loading Configuration**
The script allows saving dial configurations to a JSON file for reuse. This is particularly helpful for analyzing multiple videos with the same dial setup. Configurations include:
- **Dial centers, radii, and orientation**
- **Segment definitions and corresponding values**

To load a saved configuration, provide the file path when prompted during execution.

---

## **Contributing**
We welcome contributions to this project! You can:
- Report issues or suggest new features by opening a GitHub issue.
- Submit pull requests to enhance functionality or documentation.

Please ensure your contributions follow best practices and include descriptive commit messages.



---

## **Execution Example**
To run the script and process video files, follow the interactive prompts to:
1. Configure dials.
2. Process videos.
3. Generate outputs such as Excel files and plots.

For more advanced use, provide saved configuration files or customize parameters directly in the script.
