Go to **Model view**. Drag to create these — all **single-direction, one-to-many**, arrow pointing from the "1" (dimension) to the "*" (fact):

| From (1 side) | To (* side) |
|---|---|
| Dim_Date[Date] | Fact_Booking[BookingDate] |
| Dim_Date[Date] | Fact_Collection[DueDate] |
| Dim_Date[Date] | Fact_Lead[LeadDate] |
| Dim_Date[Date] | Fact_VendorSpend[InvoiceDate] |
| Dim_Date[Date] | Fact_Milestone[PlannedDate] |
| Dim_Project[ProjectID] | Fact_Booking[ProjectID] |
| Dim_Project[ProjectID] | Fact_Collection[ProjectID] |
| Dim_Project[ProjectID] | Fact_Lead[ProjectID] |
| Dim_Project[ProjectID] | Fact_VendorSpend[ProjectID] |
| Dim_Project[ProjectID] | Fact_Milestone[ProjectID] |
| Dim_Project[ProjectID] | Dim_Unit[ProjectID] |
| Dim_Project[ProjectID] | Dim_Agent[ProjectID] |
| Dim_Unit[UnitID] | Fact_Booking[UnitID] |
| Dim_Agent[AgentID] | Fact_Booking[AgentID] |
| Dim_Vendor[VendorID] | Fact_VendorSpend[VendorID] |
| Dim_Channel[ChannelName] | Fact_Booking[ChannelName] |
| Dim_Channel[ChannelName] | Fact_Lead[ChannelName] |
| Dim_CostHead[CostHeadName] | Fact_VendorSpend[CostHeadName] |
| Fact_Booking[BookingID] | Fact_Collection[BookingID] |

**Leave `Target_Bookings` unconnected to everything.** This is deliberate - see the note in
DAX_Measures.txt under `Booking Target YTD`. Targets are set at month-end/project grain and a relationship to a daily date table would force a fake daily allocation.