```python
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
        self.working_on : list[str] = []
        self.studying: list[str] = []
        
    def __enter__(self):
        self.working_on.extend(["EventDrivenArchitecture", "Async"])
        return super().__enter__()

    def __exit__(self, *args):
        super().__exit__(*args)
        self.working_on.clear() 
        self.studying = [next(w for w in self.working_on)] or []
```
