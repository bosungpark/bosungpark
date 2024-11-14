```go
package main

import (
	"fmt"
)

type ProgrammingLanguage string

const (
	Python ProgrammingLanguage = "python"
	Golang ProgrammingLanguage = "golang"
)

type ParkBosung struct {
	ResidesIn           string
	Company             string
	Speaks              []string
	ProgrammingLanguage ProgrammingLanguage
}

func NewParkBosung() *ParkBosung {
	return &ParkBosung{
		ResidesIn:           "🇰🇷",
		Company:             "coxwave",
		Speaks:              []string{"ko", "en", "zh-cn"},
		ProgrammingLanguage: Golang,
	}
}

func (p *ParkBosung) SpeakMe() {
	fmt.Printf("hi, my name is %s!\n", "ParkBosung")
	fmt.Printf("my current interest is server development.\n")
}

func main() {
	bosungPark := NewParkBosung()
	bosungPark.SpeakMe()
}

```
