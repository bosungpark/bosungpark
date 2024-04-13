```python
import time

from typing import Literal


class ParkBosung:
    resides_in: str = "🇰🇷"
    company: str = "looko"
    speaks: list[str] = ["ko", "en", "zh-cn"]
    programming_language: Literal["python", "golang"] =  "golang"
    interest: str | None = None
        
    def __enter__(self):
        self.interest = "server development"

        return self

    def __exit__(self, *args):
         self.interest = "system design"

    def work(self):
        print(f"most days, I'm working {self.interest} at {self.company}.\n")
        time.sleep(28800)

    def speak(self):
        print(f"hi, my name is {self.__class__.__name__}!")
        print(f"my current interest is {self.interest}.")
        
        
bosung_park = ParkBosung()
with bosung_park as worker:
    worker.work()
bosung_park.speak()

```
