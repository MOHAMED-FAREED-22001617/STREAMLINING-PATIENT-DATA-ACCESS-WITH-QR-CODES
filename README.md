# STREAMLINING-PATIENT-DATA-ACCESS-WITH-QR-CODES
## Abstract
In medical emergencies, timely access to a patient's critical information can be the difference between life and death. This project aims to develop an innovative mobile application that collects and securely stores essential medical data from patients. The application generates a QR code containing this information, which the patient can then place on the back of their mobile device. In the event of an emergency, such as a fall in a public space, a bystander or first responder can quickly scan the QR code using any standard QR reader. This scan provides immediate access to the patient's vital details, such as medical history, allergies, emergency contacts, and any other relevant health information. By enabling rapid and informed medical intervention, this application has the potential to significantly improve emergency response outcomes and save lives.
### code
```py
import qrcode
import json

# Example patient data
patient_data = {
    "name": "John Doe",
    "age": 45,
    "blood_group": "A+",
    "issue": "Hypertension",
    "last_report_date": "2024-11-01",
    "phone_number": "+1234567890"
}

# Convert patient data to JSON
patient_data_json = json.dumps(patient_data)

# Generate QR Code
qr = qrcode.QRCode(
    version=1,  # Controls the size of the QR code
    error_correction=qrcode.constants.ERROR_CORRECT_H,  # High error correction
    box_size=10,  # Size of each box in the QR grid
    border=4  # Border size (minimum is 4)
)

qr.add_data(patient_data_json)
qr.make(fit=True)

# Create the image
qr_image = qr.make_image(fill_color="black", back_color="white")

# Save the image
qr_image.save("patient_data_qr.png")
print("QR code generated and saved as 'patient_data_qr.png'")
```
### output
![WhatsApp Image 2024-11-16 at 19 06 02_a19fe9c9](https://github.com/user-attachments/assets/3cc96a01-1a58-441a-a989-e1215808a7cc)

