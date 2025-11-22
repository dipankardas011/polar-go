# EventTypes
(*EventTypes*)

## Overview

### Available Operations

* [UpdateEventType](#updateeventtype) - Update Event Type

## UpdateEventType

Update an event type's label.

### Example Usage

<!-- UsageSnippet language="go" operationID="event_types:update_event_type" method="patch" path="/v1/event_types/{id}" -->
```go
package main

import(
	"context"
	"os"
	polargo "github.com/polarsource/polar-go"
	"github.com/polarsource/polar-go/models/components"
	"log"
)

func main() {
    ctx := context.Background()

    s := polargo.New(
        polargo.WithSecurity(os.Getenv("POLAR_ACCESS_TOKEN")),
    )

    res, err := s.EventTypes.UpdateEventType(ctx, "<value>", components.EventTypeUpdate{
        Label: "<value>",
    })
    if err != nil {
        log.Fatal(err)
    }
    if res.EventType != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                | Type                                                                     | Required                                                                 | Description                                                              |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| `ctx`                                                                    | [context.Context](https://pkg.go.dev/context#Context)                    | :heavy_check_mark:                                                       | The context to use for the request.                                      |
| `id`                                                                     | *string*                                                                 | :heavy_check_mark:                                                       | The event type ID.                                                       |
| `eventTypeUpdate`                                                        | [components.EventTypeUpdate](../../models/components/eventtypeupdate.md) | :heavy_check_mark:                                                       | N/A                                                                      |
| `opts`                                                                   | [][operations.Option](../../models/operations/option.md)                 | :heavy_minus_sign:                                                       | The options for this request.                                            |

### Response

**[*operations.EventTypesUpdateEventTypeResponse](../../models/operations/eventtypesupdateeventtyperesponse.md), error**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| apierrors.HTTPValidationError | 422                           | application/json              |
| apierrors.APIError            | 4XX, 5XX                      | \*/\*                         |