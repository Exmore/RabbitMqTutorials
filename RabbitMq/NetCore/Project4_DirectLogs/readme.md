Примеры:

Запись в файл ошибок и предупреждений
cd ReceiveLogsDirect
dotnet run warning error > logs_from_rabbit.log

Вывод на экран всех типов
cd ReceiveLogsDirect
dotnet run info warning error

cd EmitLogDirect
dotnet run error "Run. Run. Or it will explode."