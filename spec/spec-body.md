## From idea to conference

#### Chicken and egg problem

Sponsor -> speakers -> visitors. But if you don't have visitors and speakers yet, only a date and a venue, what can you do?

The KERICONF uses the concept of [[ref: Tracks]] along [[ref: Lines]] that are directly connected to the objectives of the upcoming conference. 

This way you can overcome the temporary lack of final commitments and still present a great [[ref: Program]] that sponsors, speakers and visitors want to be part of.

As long as we don't have solid commitment of people, one important point to consider at all times is privacy.

### Single source of truth

Please edit program content in merge letters, emails, pdf, on the website in table always in the single source of truth and not (only) in the expression at hand.

> Google Sheet (2026 [talks-speakers-rooms](https://docs.google.com/spreadsheets/d/1bET8KvpFACJFyAIv6g0c6RSvCOg2midnu4gwI5oOOLg/edit?resourcekey=&gid=567720881#gid=567720881))

> **Tab "Talks"**
 
### Privacy

As ideas evolve about [[ref: Topics]] and possible [[ref: Speakers]], we need to carefully handle the information publicized on the web.

#### Placeholders and Obfuscation
As long as we don't have an concrete idea we use placeholders and as long as the organization doesn't have a mutual agreement on sponsorships, talks, support, or even a commitment to being a visitor: we keep the information as obfuscated as possible.

::: info
"A Dutch Airline starting with a 'K'..." is not a good example of obfuscation :) 
:::

#### Google sheet and pii
Yes, we have Google Sheets processing our dat, and we rely on their [privacy statement](https://support.google.com/docs/answer/10381817)

Reference: [Google Workspace DPA](https://workspace.google.com/terms/09242021/dpa_terms/)

[ChatGPT analysis 2025](https://chatgpt.com/share/692b081e-a584-800a-9941-73436b1df607) 

Having said this: we don't keep any sensitive data in Google sheets. Insensitive is considered:
- email
- names

#### Google Sheet and publication in the kerconf.com website

We views (tab in Google Sheet) and scripts to publish data to our site.

Scripts take care privacy preservation until the status of an agreement has a sufficient level to be safe to publish


Example script to populate a column op the program
```text
=MAP(Talks!K3:K39, Talks!G3:G39, Talks!S3:S39,
 LAMBDA(y, x, z,
  IF(
   OR(z="APPOINTED", z="RECEIVED", z="CONFIRMED"),
   IF(
    y="","",
    REGEXREPLACE(
      y,
      "\{([^}]+)\}",
      LAMBDA(key,
        IF(
          x="",
          "",
          REGEXEXTRACT(x, key & "=(.*)")
        )
      )(REGEXEXTRACT(y,"\{([^}]+)\}"))
    )
   ),
   y
  )
 ))
```
What is does, is it only replaces a variable with the actual [[ref: pii]] when the status of a Talk has a sufficient level.

### GitHub

- **Issues**
  - Source: `https://github.com/blockchainbird/kericonf-specs/issues/`
- **Pull Requests**
  - Source: `https://github.com/blockchainbird/kericonf-specs/pull/`
- **Repo**
  - Source: `https://github.com/blockchainbird/kericonf-specs/`
  - Render: https://blockchainbird.github.io/kericonf-specs/index.html