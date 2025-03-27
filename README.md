# Le-Jardin
This is a Garden Simulator. The system automates processes such as watering, temperature regulation, and pest control, reducing manual intervention. It can schedule rainfall, adjust temperature levels, and detect and manage pests, ensuring optimal garden health with minimal human effort.

Automated Gardening System - Le Jardin

When Agriculture becomes Easy


TABLE OF CONTENTS
1. Introduction……………………………………………………………………….….02
2. Requirements…………………………………………………………….……….…..03
3. User stories………………………………………………………………….………..04
4. Use Case Diagram……………………………………………………………………05
5. Activity Diagram……………………………………………………………….….…07
6. Class Diagram…………………………………………………………………..…….08
7. Object Diagram…………………………………………………………………...…..09
8. Sequence Diagram………………………………………………………………..…..10
9. Garden Setup / Running The Code Starting the Application……………………..…..11
10. Screenshots………………………………………………………………………….12
11. UI Documentation…………………………………………………………..……….14


Introduction:

Maintaining a garden requires significant effort and time to ensure plant health. The objective of this project is to develop an automated gardening system capable of monitoring and managing essential gardening tasks. The system automates processes such as watering, temperature regulation, and pest control, reducing manual intervention. It can schedule rainfall, adjust temperature levels, and detect and manage pests, ensuring optimal garden health with minimal human effort.


Problem Statement:
Gardening involves continuous attention to watering, temperature regulation, and pest management, all of which require substantial human involvement. This project aims to automate these essential processes, reducing the time and effort needed for garden maintenance while ensuring plants receive proper care.


Objectives:
	•	Automated Watering: Ensures plants receive the appropriate amount of water based on their specific needs.
	•	Temperature Regulation: Maintains optimal temperature levels to support plant growth and health.
	•	Pest Management: Detects and controls pests automatically to protect plants from damage.

Requirement Analysis:

The requirement analysis for the Automated Gardening System focuses on identifying the key functionalities needed to efficiently automate garden maintenance.

Functional Requirements - 

User Interface Requirements:
	•	A JavaFX-based interface that allows users to monitor garden status.
	•	Buttons for manually adding plants to the garden.
	•	Notifications displaying garden conditions, tasks, and weather updates.


System Operations:
	•	Watering System: Automatically irrigates plants by monitoring soil moisture and weather conditions.
	•	Temperature Control System: Regulates and maintains the optimal garden temperature.
	•	Pest Control System: Detects and manages pests using automated mechanisms.

Data Management:
	•	Logs system events, including watering schedules, temperature changes, and pest control activities.

Assumptions:
	•	The system operates with a continuous power supply and stable internet connectivity.
	•	Users have basic knowledge of operating desktop applications.

Dependencies:
	•	A weather forecasting service to provide real-time weather data.
	•	Reliable sensor technology to monitor temperature levels and detect pests.


User Stories : 

Predefined Garden Setup:
As a garden manager, I want to initialize the garden with predefined plants to easily simulate a layout without manual configurations.
Acceptance Criteria: 
The system should set up a garden with various plant types, each having predefined attributes such as water requirements.
Manual Plant Addition:
As a user, I want to manually add plants to the garden grid.
Acceptance Criteria: 
Users should be able to select and place new plants in unoccupied spaces within the garden.
Rainfall Simulation:
As a garden overseer, I want to simulate rainfall to observe how the garden distributes water to plants.
Acceptance Criteria: 
The system should allow users to trigger rain events, automatically adjusting the plants’ water levels.
Temperature Adjustment Simulation:
As a garden manager, I want to simulate temperature fluctuations to evaluate how plants react to heat and cold.
Acceptance Criteria:
Users should be able to adjust temperature settings and observe system responses.
Plants should automatically adapt to their ideal temperature conditions.
Pest Infestation Simulation:
As a user, I want to introduce parasites to study their impact on plant health.
Acceptance Criteria:
The system should allow users to simulate pest infestations.
The pest control system should automatically activate to mitigate damage and restore plant health.
Daily Garden Reports:
As a garden manager, I want to receive daily reports summarizing the garden’s condition.
Acceptance Criteria: 
The system should generate logs detailing plant health, watering schedules, pest control activities, and temperature regulation.

Use Case Diagram

Adjusting Garden Temperature:

Actor: Temperature Control System
Description: Automatically regulates the garden temperature when it deviates from the predefined threshold.
Execution Process:
First, Sensor monitors the current garden temperature. Second, The system compares the detected temperature with the optimal threshold. Finally,If an adjustment is needed, the system activates the heating or cooling mechanisms to restore ideal conditions.

Pest Detection and Management:

Actor: Pest Control System
Description: Automatically detects and manages pest infestations using an integrated pest control strategy.
Execution Process:
Sensors scan the garden for pest activity. The system identifies the detected pest type. The appropriate pest control measures are triggered to mitigate the infestation.


Planting New Plants:

Actor: Gardener (User)
Description: Users can manually plant desired plants in the garden.
Execution Process: 
The user selects and plants a new species in the garden. The Automated Gardening System takes over its care, ensuring proper watering, temperature, and pest control management.

Garden Set up & Running the Application

Launching the Application:
	•	The application’s entry point is the HelloApplication class, which extends javafx.application.Application.
	•	The start method is overridden to initialize the JavaFX stage and scene.
	•	The graphical user interface (GUI) is set up by loading the FXML layout from hello-view.fxml using FXMLLoader.

Initializing Background Services:

Once the GUI is launched, the application initializes essential background processes for the garden simulation:
	•	The WateringSystem, TemperatureSystem, and PesticideSystem are started and continuously executed.
	•	The DaySystem is initialized to simulate the progression of days within the garden.


API Simulation:
To verify the system’s functionality, the following APIs were implemented:
rain(int amount) – Simulates rainfall, triggering every 30 seconds.
temperature(int amount) – Adjusts the garden temperature every 20 seconds.
parasite(String name) – Simulates a pest attack occurring every 6 seconds.

UI Documentation

Overview:

The GardenUIController serves as the primary interface between the user and the Automated Gardening System. It provides essential tools and a visual representation for users to interact with the virtual garden. The controller manages user inputs, updates the garden layout, and dynamically reflects changes in real time. Developed using JavaFX, it ensures a responsive and interactive experience for garden simulation.


Components and Layout:
GridPane:
Displays the garden layout, where each plant is visually represented within its assigned grid cell.
Menu Buttons:
Allows users to add specific plant types, such as Trees, Flowers, or Vegetables, to the garden.
Labels:
Dynamically display key information, including:
Current day
Weather conditions
Temperature levels
Parasite status


Detailed Functionality:
Initialization:
The controller initializes the garden state when the application starts.
UI components are bound to system properties and linked to event channels using EventBus.
The garden grid is configured by setting row and column constraints based on the grid’s size.
Plant Management:
Users can interactively add plants using menu buttons.
The system checks for available spaces before adding the plant to both the data model and visual grid.
Event Handling:
The controller listens for system-wide events and updates the UI accordingly. Examples include:
Weather Updates: Displays real-time weather conditions using icons and labels.
Temperature Adjustments: Updates temperature indicators and applies visual effects to reflect changes.
Pest Attacks: Triggers animations or icons when plants are affected by parasites.
UI Updates:
Real-time updates display the garden’s state, including plant health, growth, and environmental conditions.
Ensures thread-safe updates using Platform.runLater() to modify the UI within the JavaFX application thread.


Challenges and Considerations:
Performance:
Maintaining a smooth and responsive UI, especially for large garden grids or when multiple events occur simultaneously.
Usability:
Designing an intuitive and user-friendly interface suitable for users of all experience levels.
Extensibility:
Ensuring the system is adaptable for future enhancements, such as new plant types, weather conditions, or environmental effects.


Benefits and Importance:
Troubleshooting:
Logs provide a chronological record of events leading up to errors or crashes, simplifying issue diagnosis.
Audit and Monitoring:
Continuous logging helps detect anomalies and performance issues early, improving system reliability.
Development and Testing:
Logs track execution flow and state changes, aiding debugging and ensuring correctness during development.

