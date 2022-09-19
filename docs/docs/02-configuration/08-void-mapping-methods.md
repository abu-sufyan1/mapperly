# Void mapping methods

If an existing object instance should be used as target, you can define the mapping method as void with the target as second parameter:

```csharp title="Mapper declaration"
[Mapper]
public partial class DtoMapper
{
    public partial void CarToCarDto(Car car, CarDto dto);
}
```

```csharp title="Mapper usage"
var mapper = new DtoMapper();
var car = new Car { NumberOfSeats = 10, ... };
var dto = new CarDto();

mapper.CarToCarDto(car, dto);
dto.NumberOfSeats.Should().Be(10);
```