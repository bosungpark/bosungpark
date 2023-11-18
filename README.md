```python
import time

from typing import Literal
from developer import BackendDeveloper


class ParkBosung(BackendDeveloper):
    resides_in: str = "🇰🇷"
    company: str = "looko"
    speaks: list[str] = ["ko", "en", "zh-cn"]
    programming_language: Literal["python", "golang"] =  "golang"
    
    def __init__(self):
        self.interest: str | None = None
        self.working_on: list[str] = []
        self.after_work: str | None = None
        
    def __enter__(self):
        self.working_on.extend([])
        self.interest = "DistributedSystem"
        return super().__enter__()

    def __exit__(self, *args):
        super().__exit__(*args)
        self.after_work = self.working_on.pop() or self.interest
        self.working_on.clear()
        
        
bosung_park = ParkBosung()
with bosung_park:
    print(f"most days, I'm working {bosung_park.working_on}")
    time.sleep(28800)
print(f"sometimes, I'm studying {bosung_park.after_work}")
```
