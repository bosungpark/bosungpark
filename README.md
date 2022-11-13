```python
from developer import BackendDeveloper
import FreeDGroup

class ParkBosung(BackendDeveloper):
    resides_in: str = "🇰🇷"
    company: FreeDGroup = FreeDGroup.FreeDSoft
    speaks: list[str] = ["ko", "en", "zh-cn"]
    programming_language: Python | Java =  Python
    
    def __init__(self):
        working_on : list=[str] = []
        
    def __enter__(self):
        self.working_on.extend(["EventDrivenArchitecture", "Async"])
        return super().__enter__()

    def __exit__(self, *args):
        super().__exit__(*args)
        self.working_on.clear() 
```
