# Weather-forecasting-system-
Weather forecasting system 

#include <iostream>
#include <string>
using namespace std;

int main() {
    // List of cities in Pakistan
    string cities[] = {
        "Karachi", "Lahore", "Islamabad", "Peshawar", "Quetta",
        "Faisalabad", "Rawalpindi", "Multan", "Hyderabad", "Sialkot",
        "Gujranwala", "Bahawalpur", "Sukkur", "Mardan", "Abbotabad",
        "Sargodha", "Rahim Yar Khan", "Chiniot", "Swat", "Gwadar"
    };
    const int cityCount = 20;

    // Mock weather data for each city (temperature, humidity, condition)
    int temperatures[] = {28, 24, 20, 18, 15, 25, 22, 26, 27, 23, 21, 19, 30, 17, 16, 23, 28, 22, 19, 14};
    int humidities[] = {65, 70, 50, 55, 40, 60, 58, 62, 67, 53, 52, 45, 72, 48, 43, 54, 68, 56, 50, 35};
    string conditions[] = {
        "Sunny", "Partly Cloudy", "Rainy", "Windy", "Foggy", "Cloudy", "Clear", 
        "Drizzle", "Humid", "Stormy", "Sunny", "Overcast", "Hot", "Cold", 
        "Snowy", "Foggy", "Sunny", "Partly Cloudy", "Rainy", "Windy"
    };

    // Program loop
    char choice;
    do {
        cout << "\n--- Weather Forecasting System ---\n";
        cout << "Select a city to view the weather:\n";
        
        // Display cities
        for (int i = 0; i < cityCount; i++) {
            cout << i + 1 << ". " << cities[i] << endl;
        }

        int cityChoice;
        cout << "\nEnter the number of your city (1-" << cityCount << "): ";
        cin >> cityChoice;

        // Validate input
        if (cityChoice < 1 || cityChoice > cityCount) {
            cout << "Invalid choice. Please select a valid city.\n";
        } else {
            int index = cityChoice - 1; // Adjust for 0-based indexing
            cout << "\nWeather for " << cities[index] << ":\n";
            cout << "Temperature: " << temperatures[index] << "°C\n";
            cout << "Humidity: " << humidities[index] << "%\n";
            cout << "Condition: " << conditions[index] << "\n";
        }

        // Ask if the user wants to check another city's weather
        cout << "\nWould you like to check the weather for another city? (Y/N): ";
        cin >> choice;

    } while (choice == 'Y' || choice == 'y');

    cout << "\nThank you for using the Weather Forecasting System. Goodbye!\n";
    return 0;
}
