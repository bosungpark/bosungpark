```python
import time
from developer import BackendDeveloper
import FreeDGroup


class ParkBosung(BackendDeveloper):
    resides_in: str = "🇰🇷"
    company: FreeDGroup = FreeDGroup.FREED_SOFT
    speaks: list[str] = ["ko", "en", "zh-cn"]
    programming_language: Python | Java =  Python
    
    def __new__(cls, *args, **kwargs):
        if not hasattr(cls, "_instance"):
            cls._instance = super().__new__(cls)
        return cls._instance    
    
    def __init__(self):
        self.interest: str | None
        self.working_on: list[str] = []
        self.after_work: str = "sleeping"
        
    def __enter__(self):
        self.working_on.extend(["MicroServiceArchitecture", "EventDrivenArchitecture"])
        self.interest = "DistributedSystem"
        return super().__enter__()

    def __exit__(self, *args):
        super().__exit__(*args)
        self.after_work = f"studying {next((w for w in self.working_on), None) or self.interest}"
        self.working_on.clear()
        
        
bosung_park = ParkBosung()
with bosung_park:
    print("Now, I'm working")
    time.sleep(28800)
```
