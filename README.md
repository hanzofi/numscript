# Numscript

DSL for modeling financial transactions. Declarative syntax for multi-party transfers, percentage splits, and source ordering.

## Example

```numscript
send [USD/2 10000] (
  source = @users:001
  destination = {
    90% to @merchants:042
    10% to @platform:fees
  }
)
```

## Usage

```bash
go install github.com/hanzofi/numscript/cmd/numscript@latest
numscript check script.num
numscript fmt script.num
```

## Go Library

```go
import "github.com/hanzofi/numscript"

program, err := numscript.Parse(`
  send [USD/2 1000] (
    source = @world
    destination = @users:001
  )
`)
```

## License

MIT — see [LICENSE](LICENSE)

