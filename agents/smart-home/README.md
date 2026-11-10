# Smart Home

The administrator of your Home Assistant. Smart Home does there what you would do in its
interface, faster and more consistently: it takes in new devices with you, names everything by a
scheme you chose, writes your automations and builds your dashboards — reading first, showing what
will change, and keeping a way back.

## What it does

- **New devices**: "listen for new devices" — it opens the Zigbee (ZHA or Zigbee2MQTT), Z-Wave or
  RFXCOM network, hears what joins, tells you what each device is, and asks you its name, its room
  and what to hide. Then it closes the network.
- **Names**: it proposes naming schemes with examples from your own house — `light.lustre_salon`,
  `binary_sensor.do_entree` — or takes yours, renames in bulk, and repairs the automations and
  dashboards that named the old ids.
- **Rooms, floors, labels**: created, tidied, every device placed.
- **Automations, scripts, scenes, helpers**: you say "when the front door opens at night, light
  the hall for three minutes"; it restates it, checks every entity, validates, creates, and tests
  with your agreement.
- **Dashboards**: by use and by screen — a phone, a wall tablet — as new dashboards, never over
  yours without keeping the previous version.
- **Everyday control**: "turn off the living room", "what is the temperature upstairs".
- **Health**: what Home Assistant reports as wrong, integrations in error, unavailable entities,
  low batteries, silent devices, updates waiting.

It never guesses an id, never leaves a network open, never stores a password, and cannot stop Home
Assistant or shut its machine down.

## What it needs

An imported agent arrives with no right beyond the defaults. On its Agent page:

| Setting | Why |
|---|---|
| **External services enabled: Home Assistant** | Create the service "Home Assistant" (Services page) with the address of your installation and a long-lived access token of an administrator (in Home Assistant: your profile → Security → Long-lived access tokens), test it, then allow Smart Home to use it. The token stays in Allkin. |
| **External services read only**: off | Left on, Smart Home can only read and listen. |
| **Competence: Home Assistant administration** | Its method; downloaded when you give it. |
| **Can schedule actions** + competence **Manage actions** | For a weekly health check. You approve each action it creates. |
| **Can search and read pages on the web** | To look up a device's manual or pairing gesture. Optional. |
| **Memory** (on by default) | To remember your preferences. |

## What you will see

Reading your installation asks you nothing. **Every change shows an approval card** in the
conversation — a rename, a room, a dashboard saved, a network opened — once for the whole batch,
and you may approve for the session. The service's switch **"Act without approval"** lifts the
cards for every agent, including when nobody is there: leave it off unless you want an action to
change your installation on its own.

## How to use it

1. Create the Home Assistant service and allow it on Smart Home's page.
2. Say: "Take a look at my installation." It surveys it, tells you what it found, and asks what
   you want first.
3. Then ask in your own words: "listen for new Zigbee devices", "rename the kitchen properly",
   "make a dashboard for the tablet in the hall".

## Limits

- Files written by hand in YAML (`configuration.yaml`, packages, dashboards in YAML mode) are out
  of its reach: it tells you what to change there.
- An integration that asks for an account or a password is added by you, in Home Assistant.
- It cannot see how a dashboard looks nor whether a lamp really lit: it asks you.
