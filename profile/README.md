# Mini projekt - Scanning af studiekort

## Projekter

### CardScanner
Bruger PCSC librariet til at scanne, og udtrække UID fra et studiekort, samt at sende dette videre i RabbitMQ

### DataEnricher
Modtager UID fra studiekortet, og queryer vores database for oplysninger om den studerende, samt om den studerende er tjekket ind til event(s).

### Check-In-Frontend
Giver visuel feedback til den studerende, om den enkelte studerende er tjekket ind, eller om der skete fejl i løbet af processen.

### DatabaseSetup
Opsætning af vores MySQL database



