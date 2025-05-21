def calculate_electricity_footprint(kwh_per_month):
    # Average CO2 emission: 0.417 kg CO2 per kWh (US EPA)
    return kwh_per_month * 12 * 0.417

def calculate_car_footprint(km_per_week, fuel_efficiency_km_per_liter):
    # Average CO2 emission: 2.31 kg CO2 per liter of gasoline
    liters_per_year = (km_per_week * 52) / fuel_efficiency_km_per_liter
    return liters_per_year * 2.31

def calculate_flight_footprint(short_flights, long_flights):
    # Rough estimates: short flight = 300 kg CO2, long flight = 1100 kg CO2
    return (short_flights * 300) + (long_flights * 1100)

def calculate_diet_footprint(diet_type):
    diet_impact = {
        'meat_heavy': 3.3,
        'average': 2.5,
        'vegetarian': 1.7,
        'vegan': 1.5
    }
    return diet_impact.get(diet_type.lower(), 2.5) * 1000  # in kg CO2 per year

def total_carbon_footprint(electricity, car_km, fuel_efficiency, short_flights, long_flights, diet_type):
    e = calculate_electricity_footprint(electricity)
    c = calculate_car_footprint(car_km, fuel_efficiency)
    f = calculate_flight_footprint(short_flights, long_flights)
    d = calculate_diet_footprint(diet_type)
    total = e + c + f + d
    return total

# Example usage
if _name_ == "_main_":
    electricity = float(input("Enter monthly electricity usage (kWh): "))
    car_km = float(input("Enter average weekly car travel (km): "))
    fuel_efficiency = float(input("Enter your car's fuel efficiency (km per liter): "))
    short_flights = int(input("Enter number of short flights (under 3 hours) per year: "))
    long_flights = int(input("Enter number of long flights (over 3 hours) per year: "))
    diet_type = input("Enter your diet type (meat_heavy, average, vegetarian, vegan): ")

    footprint = total_carbon_footprint(electricity, car_km, fuel_efficiency, short_flights, long_flights, diet_type)
    print(f"\nYour estimated annual carbon footprint is: {footprint:.2f} kg CO2")
