<div> 
<p align="center">
    <image src="snowflake.png" width="250" height="250">
 </p>
 <p align="center">An ID Generator for C# based on Snowflake Algorithm (Twitter announced).</p>

  <p align="center">

<a href="https://www.nuget.org/packages/Snowflake.CSharp">
      <image src="https://img.shields.io/nuget/v/Snowflake.CSharp.svg?style=flat-square" alt="nuget">
</a>

<a href="https://www.nuget.org/stats/packages/Snowflake.CSharp?groupby=Version">
      <image src="https://img.shields.io/nuget/dt/Snowflake.CSharp.svg?style=flat-square" alt="stats">
</a>
</p>

</div>

## ˵��

Twitter��ѩ���㷨SnowFlake��ʹ��csharp����ʵ�֡�


## ��װ

```
PM> Install-Package Snowflake.Data -Version 1.1.2
```

## ʹ��

1. ָ����������ID������ID.

```csharp
SnowFlake snowFlake=new SnowFlake(datacenterId:1,machineId:1);
```

2. ����ID

```csharp
var id=snowFlake.NextId();
```

## �߼�

1. ���ڷֲ�ʽ

```
PM> Install-Package Snowflake.Redis.CSharp
```

2. �� ConfigureServices() ������������´���

```csharp

public void ConfigureServices(IServiceCollection services)
{
  services.AddSnowflakeRedisService(connectionString:"127.0.0.1:6379,allowAdmin=true", 
      option 
            =>Configuration.GetSection("snowFlake").Bind(option)
     );
}
```

�ֲ�ʽѩ��ID��ͬ����ID�Զ�������

```
"snowFlake": {
  "dataCenterId": 1,
  "Name": "test"
} 
```

## License

Apache