# Discrete-Event Simulation: Water Park Operations

Simulation course project, Ben-Gurion University, 2026. Team project (4 students), Python (Google Colab).

A discrete-event simulation of a water park, built to diagnose operational problems and compare two investment plans with the same budget (₪250,000).

## The model
The simulation tracks visitors through a full day at the park:
- **Arrivals** of three visitor types: single visitors, families and teenage groups
- **Ticket purchase** at the entrance, with an optional upgrade to Express queues
- **Attractions** with regular and Express queues, including **queue abandonment** when waits get too long
- **Food court** purchases, staff lunch breaks (server release and resumption), photo sales and departures
- **Park closing** at the end of the day

## Problems identified in the current state
- Long physical ticket purchase process at the entrance, creating a bottleneck
- Low food purchase rate, leaving revenue unrealized
- Express queues with waits that are too long for a premium service
- Mass abandonment at the flagship attractions
- Unbalanced load across attractions

## Performance measures
- **Total revenue (TR):** tickets, Express upgrades, food and photos
- **Average wait in the regular queue (AW):** a direct driver of abandonment and visitor ratings

## Alternatives
| Alternative A | Alternative B |
|---|---|
| Skilled kitchen staff (fewer bad meals, more visitors eating lunch) | Larger tube ride capacity (8 → 10 seats per round) |
| Online ticketing (entrance service reduced to wristband pickup) | Online ticketing |
| Visitor welcome benefit (higher starting satisfaction) | |

## Results
Alternatives were compared with **paired t-tests**, with the number of replications set by a target relative precision.

| Comparison | Total revenue: CI of the difference | Average wait: CI of the difference |
|---|---|---|
| A vs. current | [163,810, 193,487] → A better | [2.54, 5.38] → current better |
| B vs. current | [165,776, 193,189] → B better | [−0.51, 2.30] → no significant difference |
| A vs. B | [−16,515, 14,847] → no significant difference | [2.06, 4.08] → B better |

**Conclusion:** both alternatives raise revenue by a similar amount, but Alternative A creates new bottlenecks and longer waits, while Alternative B keeps visitors flowing. **Alternative B was selected.**

## Presentation
[Full presentation](presentation/Sea_World_Simulation.pdf) (Hebrew)
