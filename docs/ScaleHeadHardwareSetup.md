# Scale Hardware Setup

#### Rice Lake 920i
1. Add the Equipment Information
    - In Levridge Scale, click Application Configuration > Equipment Management
    - Click Create New
    - Set Is active = Yes
    - Set Is scale = Yes
    - Enter Equipment Name – this is the name that will show in the UI and on printed reports
    - Equipment description – not used
    - Location – not used
    - Custom character = L
    - ***Click Save, then edit for the next two fields to be visible***
    - Equipment response type ID = 4
    - Return response type ID = 5
    - Service URL = http://localhost:5000
    - Click Save
2. Add the Equipment Field Details
    - From Equipment Management, click Edit on the Equipment record
    - Click Equipment Field Details
    - Click Create New
    - Name  = “weight”
    - SequenceId = 1
    - Check the box by OutputStreamTypeId
    - FieldName = “weight”
    - StringLength = 30
    - ReturnTypeResult = String
    - Click Create
    - Click Back to Equipment
3. Add the Connection Details
    - Click Connection Details
    - Name = 1
    - Hostname = `<ip address of scalehead>`
    - Port = 10001
    - TypeId = TcpIPClientStream
    - Click Submit
4. Create a Workstation
    - In LevridgeScale, click Application Configuration > Workstation Management
    - Click Create New
    - Enter a Workstation name, ex. “Ws1”
    - Click Create
    - Click Edit
    - Under Equipment, mark the box next to the Scale
    - Click Save
5. Configure the Hardware Service with the Workstation name
    - Navigate to the folder LevridgeScaleHouse\Services\HardwareInterface
    - Open appsettings.json
    - Enter the WorkstationName, example: "WorkstationName" : "Ws1"
6. Restart Hardware service
    - Open (Windows) Services
    - Restart LevScaleHardwareService

#### Rice Lake 1280
1. Configure the 1280
![RiceLake1280Configuration](.\assets\images\ScaleApp\RiceLake1280configuration.png)
    - Access the Scale UI in a browser. http://*<ip address of Rice Lake 1280*>:3000
    - In the Menu go to Configuration > Communications
    - Select Ethernet, TCP Client 2
    - Remote Address = <*ip address of Levridge Scale PC*>
    - Remote Port Number = 10001
2. Add the Equipment Information
    - In Levridge Scale, click Application Configuration > Equipment Management
    - Click Create New
    - Set Is active = Yes
    - Set Is scale = Yes
    - Enter Equipment Name – this is the name that will show in the UI and on printed reports
    - Equipment description – not used
    - Location – not used
    - Custom character = L
    - ***Click Save, then edit for the next two fields to be visible***
    - Equipment response type ID = 4
    - Return response type ID = 5
    - Service URL = http://localhost:5000
    - Click Save
3. Add the Equipment Field Details
    - From Equipment Management, click Edit on the Equipment record
    - Click Equipment Field Details
    - Click Create New
    - Name = “weight”
    - SequenceId = 1
    - Check the box by OutputStreamTypeId
    - FieldName = “weight”
    - StringLength = 30
    - ReturnTypeResult = String
    - Click Create
    - Click Back to Equipment
4. Add the Connection Details
    - Click Connection Details
    - Name = 1
    - Hostname = `<ip address of scalehead>`
    - Port = 10001
    - TypeId = TcpIPCStream
    - Click Submit
5. Create a Workstation
    - In LevridgeScale, click Application Configuration > Workstation Management
    - Click Create New
    - Enter a Workstation name, ex. “Ws1”
    - Click Create
    - Click Edit
    - Under Equipment, mark the box next to the Scale
    - Click Save
6. Configure the Hardware Service with the Workstation name
    - Navigate to the folder LevridgeScaleHouse\Services\HardwareInterface
    - Open appsettings.json
    - Enter the WorkstationName, example: "WorkstationName" : "Ws1"
7. Restart Hardware service
    - Open (Windows) Services
    - Restart LevScaleHardwareService

#### Serial Connection

1.	Add the Equipment Information
    - In Levridge Scale, click Application Configuration > Equipment Management
    - Click Create New
    - Set Is active = Yes
    - Set Is scale = Yes
    - Enter Equipment Name – this is the name that will show in the UI and on printed reports
    - Equipment description – not used
    - Location – not used
    - Custom character = L
    - ***Click Save, then edit for the next two fields to be visible***
    - Equipment response type ID = 4
    - Return response type ID = 5
    - Service URL = http://localhost:5000
    - Click Save
2. Add the Equipment Field Details
    - From Equipment Management, click Edit on the Equipment record
    - Click Equipment Field Details
    - Click Create New
    - Name = “weight”
    - SequenceId = 1
    - Check the box by OutputStreamTypeId
    - FieldName = “weight”
    - StringLength = 30
    - ReturnTypeResult = String
    - Click Create
    - Click Back to Equipment
3.	Add the Connection Details
    - Click Connection Details
    - Name = COM1
    - Speed = 9600
    - DataBits = 8
    - StopBits = 1
    - Parity = N
    - FlowControl = 0
    - TypeId = SerialStream
    - Click Submit
4. Create a Workstation
    - In LevridgeScale, click Application Configuration > Workstation Management
    - Click Create New
    - Enter a Workstation name, ex. “Ws1”
    - Click Create
    - Click Edit
    - Under Equipment, mark the box next to the Scale
    - Click Save
5. Configure the Hardware Service with the Workstation name
    - Navigate to the folder LevridgeScaleHouse\Services\HardwareInterface
    - Open appsettings.json
    - Enter the WorkstationName, example: "WorkstationName" : "Ws1"
6. Restart Hardware service
    - Open (Windows) Services
    - Restart LevScaleHardwareService
