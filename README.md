# microsoft-ml-
class ServiceAssistant:
    def __init__(self):
        self.state = {'location': None}

    def handle_query(self, query):
        service, location = self.parse_query(query)
        
        if service == 'weather':
            if location:
                response = f"Service: Weather, Location: {location}"
                self.state['location'] = location
            else:
                response = "Please specify the location for weather."
            return response

        elif service == 'news':
            if location:
                response = f"Service: News, Location: {location}"
                self.state['location'] = location
            else:
                response = "Please specify the location for news."
            return response

        else:
            response = "Available services: Weather, News. Please specify the service."
            return response

    def parse_query(self, query):
        # Implement query parsing logic to identify service and location
        # Return identified service and location

# Example Usage
assistant = ServiceAssistant()
query1 = "How is the weather in Bangalore?"
response1 = assistant.handle_query(query1)
print(response1)

query2 = "News for India"
response2 = assistant.handle_query(query2)
print(response2)
