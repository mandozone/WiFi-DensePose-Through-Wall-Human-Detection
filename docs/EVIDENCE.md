# Evidence guide

The gallery is a small historical record of the Docker/RuView lab. It does not establish current runtime health or detection accuracy.

| Image | What it shows | Limit |
| --- | --- | --- |
| [Container setup](../site/assets/container-setup.jpg) | Image pull and a returned container identifier | No hardware intake result is shown |
| [Local interface](../site/assets/dashboard-live.jpg) | RuView page in a local browser | Upstream interface claims are not lab measurements |
| [Heatmap](../site/assets/sensing-heatmap.jpg) | Sensing visualization from the early simulation stage | No ground-truth comparison or physical localization result |
| [Classification](../site/assets/present-moving.jpg) | Features, classification label, and a confidence display | No independent verification of a person's motion or physiology |

## Publication cleanup

The October 2026 documentation update selected a smaller set of relevant photographs, removed original embedded metadata, and kept their image pixels unchanged. Address-bearing terminal captures and the raw-image folder were removed from the current tree. A previously mislabeled board photo was also removed rather than used as evidence of an ESP32-S3 build.

Earlier commits may retain removed files. Removing a current file does not purge Git history. Do not repost the earlier unreviewed originals.

## Adding future evidence

Record the application/image revision, firmware revision, source mode, logical node count, test conditions, and observed result. Remove private connection information and image metadata before publishing. A useful caption states both what a picture establishes and what remains to be checked.
