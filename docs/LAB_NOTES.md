# Lab notes

These notes summarize the early deployment experiment and the checks needed to repeat it responsibly. Exact installation commands depend on the chosen upstream revision; no application source is included in this repository.

## Recorded troubleshooting

| Issue encountered | Historical response | Lesson for the next run |
| --- | --- | --- |
| VM name resolution failed | Resolver configuration was corrected | Check name resolution separately from basic connectivity; retain actual resolver details privately |
| Compose command was unavailable | The lab's Compose tooling was installed/configured | Confirm whether the environment uses the current Docker plugin or a legacy standalone tool |
| Dashboard route returned an error | The lab refreshed its image and checked the UI assets/route | Record the image digest and verify the route instead of assuming every image tag has the same layout |
| Multi-line Docker command failed | Command formatting was corrected | The image name must remain part of the same command; review pasted continuations |
| Interface looked active without hardware proof | Simulation was documented explicitly | Use receiver data and controlled disconnect tests to establish hardware integration |

## Read-only checks

Use the commands that apply to your installation, and keep unredacted output private:

```bash
docker --version
docker compose version
docker ps --format 'table {{.Names}}\t{{.Status}}\t{{.Image}}'
```

After identifying the intended container, inspect its logs locally. Confirm its exact image revision, UI route, and declared data source. Do not publish complete logs before checking for addresses, credentials, device identifiers, and private paths.

## Transport roles in this historical experiment

| Service | Recorded port | Interpretation |
| --- | --- | --- |
| HTTP interface | TCP 3000 | A reachable page is evidence of the web layer only |
| WebSocket service | TCP 3001 | An established connection still needs correctly decoded data |
| Sensor intake | UDP 5005 | Packet arrival must be matched to the intended node and payload format |

The Docker photograph records the launch used at that time. Port mappings can make services reachable beyond the intended browser; confirm the binding and network policy for a new installation. Addresses and private host mappings are deliberately absent from these notes.

## Next hardware experiment

1. Record the exact board and firmware revision.
2. Use one logical node and an explicitly configured receiver.
3. Confirm receiver-side packets and successful decoding.
4. Correlate timestamps or sequence values with the dashboard.
5. Disconnect the node and observe a stale state; reconnect and verify recovery.
6. Only then add another node or begin a controlled sensing experiment.

Do not equate generic network traffic with CSI samples, or a rendered heatmap with validated sensing. The broader AHSIN work has its own historical milestones and needs its own repeatable integration record.
