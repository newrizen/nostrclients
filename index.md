---
layout: home
---

Compendium of nostr clients and known features.

Contribute on github: <{{ site.github.repository_url }}>

## Legend

- [NIPs](https://github.com/nostr-protocol/nips)
- ✅ : mostly supported
- 🟡 : partially supported
- ❌ : mostly not supported
- ⚡ : paid feature
- `?` : reviewed but inconclusive
- <code>&nbsp;</code> : not yet reviewed

<div class="bigtable">
<table>
  <thead>
    <tr>
      <!-- Basic Info -->
      <th>Client \ Feature (NIP) [Kind]</th>
      <th>Source Repository</th>
      <th>Last Reviewed Version/Date</th>
      <th>Primary Purpose</th>
      <!-- Features -->
      {% for feature in site.data.features %}
      <th>{{ feature[1] }}</th>
      {% endfor %}
    </tr>
  </thead>
  <tbody>
    {% for client_order in site.data.order %}
    {% for client_hash in site.data.clients %}
    {% if client_hash[0] == client_order %}
    {% assign client = client_hash[1] %}
    <tr>
      <!-- Basic Info -->
      {% if client.site %}
      <td><a href="{{ client.site }}">{{ client.alias }}</a></td>
      {% else %}
      <td>{{ client.alias }}</td>
      {% endif %}
      <td><a href="{{ client.repo }}">{{ client.repo | split: "://" | last | split: "/" | first }}</a></td>
      <td>{{ client.latest }}</td>
      <td>{{ client.purpose }}</td>
      <!-- Features -->
      {% for feature_head in site.data.features %}
      <td>
      {% for feature_client in client.features %}
      {% if feature_client[0] == feature_head[0] %}
      {{ feature_client[1] }}
      {% endif %}
      {% endfor %}
      </td>
      {% endfor %}
    </tr>
    {% endif %}
    {% endfor %}
    {% endfor %}
  </tbody>
</table>
</div>


## Similar projects

- <https://github.com/aljazceru/awesome-nostr>
- <https://github.com/vishalxl/Nostr-Clients-Features-List>
- [Nostr Client Comparison Sheet (Google Docs)](https://docs.google.com/spreadsheets/d/1GjfN_eMiEywqXfKFHZMw4rLnoQLBXYEyl2NCEtsCXWw/edit)
- <https://nostr.info/resources/>
- <https://nostr.com/clients>
- <https://www.nostrapps.com/>
- <https://nostrapp.link/>
