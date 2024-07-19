
import pandas as pd

data = [
    {
        "_id": "T6hf3rb5",
        "appointmentId": "40d2-9c9f",
        "patientDetails": {
            "_id": "T6hb630b3",
            "firstName": "Css",
            "lastName": "",
            "emailId": "",
            "gender": "",
            "alternateContact": "",
            "birthDate": None
        },
        "phoneNumber": "96686896670",
        "consultationData": {}
    },
    {
        "_id": "T65g3rb5",
        "appointmentId": "40dbtc9f",
        "patientDetails": {
            "_id": "T6h33b300",
            "firstName": "Lokesh",
            "lastName": "",
            "emailId": "",
            "gender": "M",
            "birthDate": "1996-05-16T18:30:00.000Z"
        },
        "phoneNumber": "9496368916",
        "consultationData": {}
    },
    {
        "_id": "T7g6Srb5",
        "appointmentId": "g3Wt5c9f",
        "patientDetails": {
            "_id": "TjhB4373",
            "phrId": "63b5hvy614d5",
            "firstName": "Shila",
            "lastName": "Das",
            "emailId": ""
        },
        "phoneNumber": "7787204833",
        "consultationData": {}
    },
    {
        "_id": "94bg8W8d",
        "appointmentId": "fb6-a535",
        "patientDetails": {
            "_id": "6df4R5b",
            "phrId": "644nig7y",
            "firstName": "Bhavika",
            "lastName": "Ben Panchal",
            "emailId": "",
            "gender": "F",
            "birthDate": "1988-04-24T14:30:00.000Z"
        },
        "phoneNumber": "9376756879",
        "consultationData": {}
    }
]

# Extract relevant data into a list of dictionaries
patient_data = [
    {
        "gender": item["patientDetails"].get("gender")
    } for item in data
]

# Create a DataFrame
df = pd.DataFrame(patient_data)

# Impute missing genders with the mode
df['gender'].fillna(df['gender'].mode()[0], inplace=True)

# Calculate percentage of female gender
female_percentage = (df['gender'] == 'F').sum() / len(df) * 100

# Print result
print(female_percentage)
import pandas as pd

data = [
    {
        "_id": "T6hf3rb5",
        "appointmentId": "40d2-9c9f",
        "patientDetails": {
            "_id": "T6hb630b3",
            "firstName": "Css",
            "lastName": "",
            "emailId": "",
            "gender": "",
            "alternateContact": "",
            "birthDate": None
        },
        "phoneNumber": "96686896670",
        "consultationData": {}
    },
    {
        "_id": "T65g3rb5",
        "appointmentId": "40dbtc9f",
        "patientDetails": {
            "_id": "T6h33b300",
            "firstName": "Lokesh",
            "lastName": "",
            "emailId": "",
            "gender": "M",
            "birthDate": "1996-05-16T18:30:00.000Z"
        },
        "phoneNumber": "9496368916",
        "consultationData": {}
    },
    {
        "_id": "T7g6Srb5",
        "appointmentId": "g3Wt5c9f",
        "patientDetails": {
            "_id": "TjhB4373",
            "phrId": "63b5hvy614d5",
            "firstName": "Shila",
            "lastName": "Das",
            "emailId": ""
        },
        "phoneNumber": "7787204833",
        "consultationData": {}
    },
    {
        "_id": "94bg8W8d",
        "appointmentId": "fb6-a535",
        "patientDetails": {
            "_id": "6df4R5b",
            "phrId": "644nig7y",
            "firstName": "Bhavika",
            "lastName": "Ben Panchal",
            "emailId": "",
            "gender": "F",
            "birthDate": "1988-04-24T14:30:00.000Z"
        },
        "phoneNumber": "9376756879",
        "consultationData": {}
    }
]

# Extract relevant data into a list of dictionaries
patient_data = [
    {
        "firstName": item["patientDetails"].get("firstName"),
        "lastName": item["patientDetails"].get("lastName"),
        "birthDate": item["patientDetails"].get("birthDate")
    } for item in data
]

# Create a DataFrame
df = pd.DataFrame(patient_data)

# Calculate percentage of missing values
missing_percentage = df.isnull().sum() / len(df) * 100

# Print results in the desired format
print("{:.2f},{:.2f},{:.2f}".format(missing_percentage["firstName"], missing_percentage["lastName"], missing_percentage["birthDate"]))
