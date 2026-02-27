# Intent-to-Plugin Matching Logic

## Matching Strategy

Match user intent against the plugin catalog using a weighted scoring approach.

### Signal Sources (by priority)

1. **Keywords match** (highest weight) — direct match between user terms and plugin `keywords` array
2. **Description match** — semantic overlap between user request and plugin `description`
3. **Tags match** — match against plugin `tags` for broad category alignment
4. **Name match** (lowest weight) — plugin name appears in user request

### Scoring Rules

- Exact keyword match: +3 points per keyword
- Description term overlap: +2 points per meaningful term
- Tag match: +1 point per tag
- Name match: +1 point

Select the plugin with the highest score. If the top two scores are within 2 points of each other, present both as options.

## Current Plugin Catalog

NOTE: This is a reference snapshot. Always read `marketplace.json` as the source of truth — the catalog below may be outdated as new plugins are added.

### deploy-on-aws

| Field    | Values                                                                                                                                         |
| -------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| Keywords | aws, aws agent skills, amazon, deploy, cdk, cloudformation, infrastructure, pricing                                                            |
| Tags     | aws, deploy, infrastructure, cdk                                                                                                               |
| Triggers | "deploy to AWS", "host on AWS", "run this on AWS", "AWS architecture", "estimate AWS cost", "generate infrastructure", "CDK", "CloudFormation" |

### amazon-location-service

| Field    | Values                                                                                                                                          |
| -------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| Keywords | location, maps, geocoding, routing, places, geofencing, tracking, amazon-location, maplibre, address, coordinates                               |
| Tags     | aws, location, maps, geospatial                                                                                                                 |
| Triggers | "add a map", "geocoding", "routing", "places search", "geofencing", "tracking", "MapLibre", "location service", "address lookup", "coordinates" |

## Ambiguity Resolution

When intent is ambiguous:

- Present top matches as a numbered list with one-sentence rationale each
- Ask user to select: "Which plugin best fits your needs?"
- Do NOT auto-install when ambiguous

## No-Match Indicators

A request likely has no match when:

- No plugin scores above 2 points
- User mentions technologies/services not in any plugin's keywords
- Request is outside the AWS ecosystem entirely
