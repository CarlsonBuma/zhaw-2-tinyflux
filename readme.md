# Zeitreihen Datenspeicher
 - Measurement: TABLE (STRING)
 - Point: Record => Row / Entry
 - Attributes:
    - time: datetime => ID
    - tags: object
    - fields: object 

## Example Create
p1 = Point(
    measurement="city temperatures",
    time=datetime(2022, 1, 1, tzinfo=timezone.utc),
    tags={"city": "Greenwich", "country": "England"},
    fields={"high": 52.0, "low": 41.0}
)

## Logic '&', '|', '~' (NOT), '=='
t1 = datetime(2010, 1, 1, tzinfo=timezone.utc)
t2 = datetime(2020, 1, 1, tzinfo=timezone.utc)
db.search((Time >= t1) & (Time < t2))

## Unique Tags