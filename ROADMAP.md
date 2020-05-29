# Roadmap
The roadmap of nest.land with goals and resource costs included.


## Milestone 1
This milestone represents our first public release (MVP 1).
Following release, we will place a strong emphasis on marketing in order to gain traction with the Deno community.

### Goals
  - Site:
    - Basic analytics for the website (Google Analytics or FOSS alternative).
    - Functioning Database + API that maps files to a nest.land URI (see resources goal 1).
  - CLI:
    - User Accounts
      - A global user account API key will be stored in `~/.nest-land-creds` where the CLI shall retreive them.
  - API:
    - Versions must be SemVer (2.0.0) compliant.
    - Package names must be alphanumeric.
    - https://x.nest.land/package[@version]/[someFile].(ts/js)
      - Proxy to the files stored on Arweave, data required stored in database.
    - https://api.nest.land/packages
      - `GET` -> Get a list of packages.
    - https://api.nest.land/info/<package[@version]>
      - `GET`  -> Get package metadata.
    - https://api.nest.land/publish/<name@version>
      - `POST` -> New package
      - `PUT`  -> Update package
    - https://api.nest.land/signup
      - `POST` -> Create a new account, argon2 hash, provides an API key.
    - https://api.nest.land/login
      - `POST` -> Logs into the account, provides an API key.
 - Website:
    - Basic UI for information about the service and documentation for how to begin.
    - Gallery to view and search packages on the registry (utilizing the API).


### Resources:
  - [PostgresSQL On Digital Ocean ($15/month)](https://www.digitalocean.com/products/managed-databases-postgresql/)
  - [VPS - Option 3 (3GB RAM  1vCPU  3TB Storage  60GB SSD 	$15/MO)](https://www.digitalocean.com/pricing/)
  - Average Package Size -> 50kb to 400kb -> 0.000088482632 AR to 0.000670494050 AR per transaction


## Milestone 2
In this milestone, we'd like to continue adding minor features to the service to improve user experience and security.
We'd also like to implement premium features to allow for profitability on the team's end.

### Goals
  - API:
    - Enforce cryptographic signing for all users (GPG keys).
    - All routes are ratelimited using a per-route token (paired with a cooldown) for storage in a client side bucket.
    - Implement contributor keys to allow for multiple publish sources. (Paywall for more than 3 people, $5 per person)
      - Paywall for more than 3 people, $5 per person
    - GraphQL API instead of REST.
      - Depending on the libraries available for Deno, this may consitute a rewrite to rust for the API.
  - Site:
    - Transition to TypeScript for Deno compatibility

### Resources
  - Everything in Milestone 1
  - [Vercel Teams ($40/month)](https://vercel.com/pricing)


## Milestone 3
Milestone 3 consists of continuing to grow our userbase while introducing more powerful analytics software to fine-tune the service.
 
### Goals
  - Random testing, some users may be served release candidates of nest.land in order to test if they function or not,
    this could be orchestrated through k8s or Docker (maybe).
  - 

### Resources
  - Digital Ocean Kubernetes if scale demands it. Pricing varies on cluster sizing and network traffic.