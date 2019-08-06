Примеры:
ReceiveLogsTopic
dotnet run "#"

ReceiveLogsTopic
dotnet run "kern.*"

ReceiveLogsTopic
dotnet run "*.critical"

ReceiveLogsTopic
dotnet run "kern.*" "*.critical"

EmitLogTopic
dotnet run "kern.critical" "A critical kernel error"