Keyword : [[Data Pipeline]], [[ESP (Event Stream Platform)]], [[Data Loading]]
- **Event Definition**: An event represents an observable state update over time, such as GPS coordinates or temperature readings.
    
- **Common Event Formats**:
    - Primitive types (text, number, date)
    - Key-value pairs (can include complex types like JSON or XML)
    - Often associated with timestamps for time sensitivity.
- **Event Streaming**:
    - Involves continuous transportation of events from sources (like sensors or applications) to destinations (like databases or file systems).
    - Can be complex with multiple sources and destinations using different communication protocols (e.g., FTP, HTTP).

![[EventProblem.png]]Problem: Complex Scenario to implement if individual event go to different source
-> [[ESP (Event Stream Platform)]] to centralize and control event source and destination
![[ESPcomponent.png]]