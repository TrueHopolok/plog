# Pretty logger package

Contain a customly written logger with methods:
- `Debug/Info/Warn/Error/Fatal` - for printing logs;
- `Set methods` - to change output information, format, logger level;
- `fmt.Fprintf` - all logs act as formating printing function but with addition of log information.

---

### Example usage:
```go
// create new logger that output
// - messages on level info or higher
// - output in stdout
// - output timestamp, caller function and the logger level
// - have a colorful output in console via ANSI sybmols
logger, _ := plog.NewLogger(plog.LevelInfo, os.Stdout, plog.RequireAll, false)

// output required information and "Hello world!"
logger.Info("Hello world!") 

// do nothing since level is too low
logger.Debug("something") 

// output empty line
logger.Line() 

// output warning log with "Warning" string
logger.Log(plog.LevelWarn, "Warning") 

// output varaible value as info level log
logger.Log(plog.LevelInfo, "variable=%d", variable) 
```
