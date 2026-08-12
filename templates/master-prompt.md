# Master Prompt Template — Model Photo World Extension

Edit the supplied original photograph.

## REFERENCE ROLES

Image A is the direct edit target and absolute geometry reference.
If Image B is provided, use it only as an atmosphere and lighting reference, never as a geometry reference.

## STRICT GEOMETRY PRESERVATION

Preserve exactly as photographed:

- [SUBJECT / MODEL]
- [TRACKS / ROAD / GROUND STRUCTURE]
- [BARRIERS / SIGNALS / STREET FURNITURE]
- [BUILDINGS / TREES / PROPS]
- [TEXT / LOGOS / ROUTE SIGNS]
- camera position, perspective, composition, and depth of field

Do not regenerate, redraw, reshape, replace, simplify, smooth over, obscure, relocate, or reinterpret existing foreground geometry.

## EDITABLE AREA

Modify only:

- [BACKGROUND AREA]
- [SPECIFIED LIGHT SOURCES]
- [SPECIFIED ATMOSPHERE]

## WORLD SETTING

Location: [LOCATION]
Season: [SEASON]
Time: [TIME]
Air/weather: [AIR]
Distant evidence: [DISTANT CUES]

Keep background distant, dark, soft, low-contrast, restrained, and out of focus.

## LIGHTING HIERARCHY

Keep only the light sources that physically exist in the photographed subject or that the user explicitly requests. Delete every non-applicable item; never invent a vehicle, signal, display, or interior light merely to fill the template.

1. [DOMINANT PRACTICAL LIGHT]
2. [HEADLIGHT / OPERATIONAL LIGHT]
3. [WARNING LIGHT]
4. [ROUTE / DESTINATION DISPLAY]
5. [INTERIOR LIGHT]
6. [DISTANT LIGHTS]

## PHYSICAL SURFACE INTERACTION

Edit illumination only.
Do not create new painted light patches.
Allow existing photographed surfaces to catch reflected light first.
Preserve all grooves, tracks, seams, textures, and markings beneath the light.

## AVOID

No geometry changes.
No invented lamps.
No invented light sources added only to complete the template.
No text changes.
No modern LED look unless correct for the subject.
No HDR shadow lift.
No excessive bloom.
No cinematic light cone.
No scenic-tourism background.
No added crowds/vehicles unless explicitly requested.

## FINAL PRIORITY

If any requested aesthetic improvement would require changing original geometry, preserve original geometry and omit that improvement.

The final image should feel like the same original photograph with only physically plausible environmental extension and operational lighting added.
