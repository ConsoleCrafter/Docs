# 🎉 SkCord

[![GitHub release](https://img.shields.io/github/v/release/Fedustria/SkCord?style=flat-square)](https://github.com/Fedustria/SkCord/releases)
[![Spigot](https://img.shields.io/badge/Spigot-Compatible-brightgreen?style=flat-square)](https://www.spigotmc.org/)
[![License](https://img.shields.io/github/license/Fedustria/SkCord?style=flat-square)](https://github.com/Fedustria/SkCord/blob/master/LICENSE)

**SkCord** is a powerful **Spigot plugin** that allows you to interact directly with Discord webhooks from your Minecraft server. It provides effects and expressions for sending, editing, and deleting messages, as well as creating rich embeds.

---

## ⚡ Features

* **Send Webhook Messages**: Easily send messages to any Discord channel using a webhook URL.
* **Edit & Delete Messages**: Modify or remove messages sent via a webhook.
* **Rich Embeds**: Create complex and visually appealing embeds with author, fields, footer, and images.
* **Metrics Integration**: Various charts to visualize plugin usage.

---

## 🚀 Getting Started

### Prerequisites

* A **Spigot/Paper Minecraft Server**
* A **Discord server with a webhook URL**

### Installation

1. Download the latest **skCord-v3-3.3-SNAPSHOT.jar** from the [release page](https://github.com/Fedustria/SkCord/releases).
2. Place the JAR file in your `plugins/` folder.
3. Restart your server to generate the configuration files.

---

## ✨ Skript Syntaxes

SkCord extends **Skript** with new effects and expressions.

### 1️⃣ Sending Webhook Messages

```skript
send webhook %string% with message %string%
```

**Example:**

```skript
on join:
    send webhook "YOUR_WEBHOOK_URL_HERE" with message "%player% joined the server!"
```

---

### 2️⃣ Editing Webhook Messages

```skript
edit webhook message %string% with id %string% and new message %string%
```

**Example:**

```skript
command /editmessage <text>:
    trigger:
        edit webhook message "YOUR_WEBHOOK_URL" with id "MESSAGE_ID_HERE" and new message "This message has been edited by an admin."
```

---

### 3️⃣ Deleting Webhook Messages

```skript
delete webhook message %string% with id %string%
```

**Example:**

```skript
command /deletemessage <text>:
    trigger:
        delete webhook message "YOUR_WEBHOOK_URL" with id "MESSAGE_ID_HERE"
```

---

### 4️⃣ Creating Rich Embeds

#### Embed Builder Section

```skript
[embed builder]:
    # Add embed fields here
```

**Example:**

```skript
command /announce <text>:
    trigger:
        set {_webhook} to "YOUR_WEBHOOK_URL_HERE"
        send webhook {_webhook} with embed:
        [embed builder]:
            set title of embed to "Server Announcement"
            set description of embed to "%arg 1%"
            add embed field "Announcer" with value "%player%"
            set footer of embed to "%player%" with icon url "%player's skin url%"
```

---

#### Embed Expressions

* **Author**

```skript
embed author with name %string% [and icon url %string%] [and url %string%]
```

**Example:**

```skript
set author of embed to embed author with name "Server Team"
```

* **Field**

```skript
embed field %string% with value %string% [and inline %boolean%]
```

**Example:**

```skript
add embed field "Server Status" with value "Online"
```

* **Footer**

```skript
embed footer with text %string% [and icon url %string%]
```

**Example:**

```skript
set footer of embed to embed footer with text "Announced by Admin"
```

* **Image**

```skript
embed image with url %string%
```

**Example:**

```skript
set image of embed to embed image with url "https://example.com/image.png"
```

---

## 📊 Metrics

SkCord collects various metrics to visualize plugin usage:

* `Advanced Bar Chart`
* `Advanced Pie Chart`
* `Custom Chart`
* `Drilldown Pie Chart`
* `Multi-Line Chart`
* `Simple Bar Chart`
* `Simple Pie Chart`
* `Single-Line Chart`

These metrics help developers understand how the plugin is being used and improve it in future updates.

---

## 🛠 Support

If you encounter issues, have questions, or want to suggest a feature:
[Open an Issue on GitHub](https://github.com/Fedustria/SkCord/issues)

---

✨ **Enjoy using SkCord!**
