# Sleep Fitter Data JSON Integration

This document provides a detailed explanation of each field within the `Sleep Fitter Data Example` JSON structure, clarifying its purpose and expected content.

---

## Top-Level Fields

* **`tableName`** (string):
    * **Description**: This field is a placeholder for the name of the airtable table  where this sleep data would be stored. It helps in organizing and identifying data.
    * **Example Value**: `"sleep_fitter_records"`

* **`firstName`** (string):
    * **Description**: Represents the first name of the participant for whom the sleep analysis was conducted. Used for personalization and identification.
    * **Example Value**: `"Dale"`

* **`userEmail`** (string):
    * **Description**: Intended to hold the participant's email address.
    * **Example Value**: `"dale@example.com"`

* **`responseId`** (string):
    * **Description**: A unique identifier assigned to each individual survey response.
    * **Example Value**: `"recLJBHCaXrsJdzTC"`

---

## `sleepFitterScore` Object

This object encapsulates all details related to the participant's overall Sleep Fitter™ Score.

* **`score`** (string):
    * **Description**: The score obtained by the participant from the Sleep Fitter™ survey.
    * **Example Value**: `"26"`

* **`percentage`** (string):
    * **Description**: The participant's Sleep Fitter™ score expressed as a percentage. This provides a quick, normalized view of their sleep health.
    * **Example Value**: `"20"`

* **`summary`** (string):
    * **Description**: This field contains the AI-generated summary of the participant's overall sleep survey.
    * **Example Value**: `"Your sleep assessment reveals several significant concerns that require immediate attention. Getting only 2 hours of sleep per night is severely below the recommended 7-9 hours for adults. You've reported having sleep apnea and GERD, which can significantly impact sleep quality. While you fall asleep relatively quickly at 30 minutes, the combination of these health conditions and extremely short sleep duration is concerning. Temperature regulation appears to be a challenge, with reports of discomfort from hot weather affecting your sleep quality."`

* **`category`** (string):
    * **Description**: The classification of the participant's sleep quality based on their `score` and the defined Sleep Fitter™ Score Scale (e.g., 'Excellent Sleep', 'Good Sleep', 'Need Improvement', 'Poor Sleep').
    * **Example Value**: `"Poor Sleep"`

---

## `statisticalAnalysis` Object

This object provides statistical comparisons of the participant's score against relevant demographics or groups.

* **`ageRangeAverageScore`** (string):
    * **Description**: The average Sleep Fitter™ score for respondents within the participant's age range (e.g., 52). 
    * **Example Value**: `"83.92"`

* **`roleAverageScore`** (string):
    * **Description**: The average Sleep Fitter™ score for individuals in the participant's professional role or industry (e.g., Business and Finance).
    * **Example Value**: `"66"`

---

## `sleepQuality` Object

This object details both self-reported and objective aspects of the participant's sleep quality.

* **`overallRating`** (string):
    * **Description**: The participant's subjective self-assessment of their overall sleep quality.
    * **Example Value**: `"Fairly good"`

* **`summary`** (string):
    * **Description**: This field contains the AI-generated summary descriptive text providing context to the `overallRating`.
    * **Example Value**: `"You rated your overall sleep quality as 'Fairly good,' though your objective measures suggest significant room for improvement."`

---

## `healthConditions` (array of strings):

This field lists specific health conditions reported by the participant that might affect sleep.

* **Description**: An array containing the names of all health conditions the participant has reported being diagnosed with that may affect their sleep. This allows for a flexible list of conditions without boolean flags.
* **Possible Values (based on the survey options)**: `"Sleep Apnea"`, `"Acid Reflux"`, `"GERD"`, `"Migraine"`, `"Disease(s) that effect your breathing"`, `"Disease(s) that effect circulation"`
* **Example Value**: `["Sleep Apnea", "GERD"]`

---

## `sleepDuration` Object

This object provides details about the participant's sleep duration.

* **`currentHours`** (string):
    * **Description**: The approximate number of hours the participant currently sleeps per night.
    * **Example Value**: `"2"`

* **`recommendedHoursRange`** (string):
    * **Description**: The generally recommended range of sleep hours for adults, providing a target for improvement.
    * **Example Value**: `"7-9 hours"`

---

## `suggestionsForImprovement` Array

This is an array of objects, where each object represents a category of suggestions for improving sleep.

* **`category`** (string):
    * **Description**: The thematic grouping for a set of suggestions (e.g., 'Sleep Duration', 'Medical Management').
    * **Example Value**: `"Temperature Regulation"`

* **`suggestions`** (array of strings):
    * **Description**: An array containing specific, textual recommendations related to the `category`. These are the actionable steps the participant can take.
    * **Example Values (for "Temperature Regulation" category)**:
        * `"Maintain bedroom temperature between 60-68°F (15.6-20°C)"`
        * `"Use moisture-wicking bedding materials"`
        * `"Consider a cooling mattress pad or temperature-regulating bedding"`

---
