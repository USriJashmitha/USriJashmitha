import React, { useState } from 'react';

const WeatherApp = () => {
    const [location, setLocation] = useState('');
    const [weatherData, setWeatherData] = useState(null);
    const [loading, setLoading] = useState(false);
    const [error, setError] = useState('');

    const API_KEY = 'your_api_key'; // Replace with your actual API key
    const API_URL = `https://api.openweathermap.org/data/2.5/forecast?q=${location}&cnt=6&units=metric&appid=${API_KEY}`;

    const fetchWeatherData = async () => {
        try {
            setLoading(true);
            const response = await fetch(API_URL);
            if (!response.ok) {
                throw new Error('Weather data not available');
            }
            const data = await response.json();
            setWeatherData(data);
            setLoading(false);
            setError('');
        } catch (error) {
            setError('Error fetching weather data');
            setLoading(false);
            setWeatherData(null);
        }
    };

    const handleSubmit = (e) => {
        e.preventDefault();
        fetchWeatherData();
    };

    return (
        <div>
            <h1>Weather Forecast</h1>
            <form onSubmit={handleSubmit}>
                <input
                    type="text"
                    value={location}
                    onChange={(e) => setLocation(e.target.value)}
                    placeholder="Enter city"
                    required
                />
                <button type="submit">Get Weather</button>
            </form>

            {loading && <p>Loading...</p>}
            {error && <p>{error}</p>}

            {weatherData && (
                <div>
                    <h2>Current Weather</h2>
                    <p>Temperature: {weatherData.list[0].main.temp}°C</p>
                    <p>Condition: {weatherData.list[0].weather[0].description}</p>

                    <h2>Forecast for Next 5 Days</h2>
                    <ul>
                        {weatherData.list.slice(1, 6).map((item, index) => (
                            <li key={index}>
                                {item.dt_txt}: {item.main.temp_min}°C - {item.main.temp_max}°C, {item.weather[0].description}
                            </li>
                        ))}
                    </ul>
                </div>
            )}
        </div>
    );
};

export default WeatherApp;
