```python
import time

from typing import Literal
from developer import BackendDeveloper


class ParkBosung(BackendDeveloper):
    resides_in: str = "🇰🇷"
    company: str = "looko"
    speaks: list[str] = ["ko", "en", "zh-cn"]
    programming_language: Literal["python", "java", "golang", "c++"] =  "golang"
    
    def __init__(self):
        self.interest: str | None = None
        self.working_on: list[str] = []
        
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
