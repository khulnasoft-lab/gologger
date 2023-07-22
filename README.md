# gologger

gologger is a very simple logging package to do structured logging in go. 

### Use gologger as a library

```go
package main

import (
	"strconv"

	"github.com/khulnasoft-labs/gologger"
	"github.com/khulnasoft-labs/gologger/levels"
)

func main() {
	gologger.DefaultLogger.SetMaxLevel(levels.LevelDebug)
	//	gologger.DefaultLogger.SetFormatter(&formatter.JSON{})
	gologger.Print().Msgf("\tgologger: sample test\t\n")
	gologger.Info().Str("user", "pdteam").Msg("running simulation program")
	for i := 0; i < 10; i++ {
		gologger.Info().Str("count", strconv.Itoa(i)).Msg("running simulation step...")
	}
	gologger.Debug().Str("state", "running").Msg("planner running")
	gologger.Warning().Str("state", "errored").Str("status", "404").Msg("could not run")
	gologger.Fatal().Msg("bye bye")
}
```

gologger is made with 🖤 by the [khulnasoft-labs](https://khulnasoft-labs.io) team.