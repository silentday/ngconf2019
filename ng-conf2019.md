# ng-conf 2019

## Keynote

### Angular 8
- Out end of May
- Can try the Version 8rc

#### Differential Loading
- 2 bundles, one for ES5 and one for Modern Syntax
- Will work with SEO
- Save 7-20% 

#### CLI Updates
- Builders -> Deploy -> WebWorkers -> Service Worker Improvements
- Lazy Loading via import()
- Better IDE Completions and Getting Started guide

### Bazel
- Core building system
- Orchestrator
- Incremental build and test
- Full-stack
- Scale on the Cloud - ReUse Test Artifacts
- Can use Bazel in Angular CLI with Angular 8

### Ivy
- next.angular.io
- Few Dependencies - low risk, Many dependencies - high risk
- Breakpoint in HTML, Debuggable stack
- Recommended, View Engine + Differential
- Help test Ivy + Differential
- Version 9 Ivy is Default and Bazel in CLI is featrued and Stable
- Angular photon - scale up 
- Angular is open source google runs on development HEAD from github
- Angular Collaborators - Community/Enterprise

## Control Value Accessor

- An interface between angular form and DOM
- Great for Granular control
- keep wrappers dumb




## Elements

- Lazy load with document object
- ngx-build-plus - single bundle flag
- reuse with other frameworks
- IVY will help with bundle issues.

##Interceptors

- Black hole interceptors - Add http auth token to the header, clone the orginal request.
- Custom headers
- Logging
- Caching
- loader
- General Notifications
- Error Handling

Rollout.io + Launch Darkly => CDN Features

## Angular tips

### RxJS
- How to manage multiple observable subscriptions?
  + subSink - add all subscriptions to sub array, on destroy unsubscribe


### State Management
* How do you scale?
  - NgRX Data - Convention based CRUD
  + Now merged in v8 ngrx

### Cloud Services
* JAM Stack - https://jamstack.org/
* aka.ms/code-functions, code-storage, code-az

## Make it fast
* Code Minification/dead code
* Differential loading!!!
  - Load html, look at scrit tags, download right version
  - script no module, vs type="module"
  - proposal for browser standard
  - angular cli v8
  - set target in tsconfig.json to es2015
  - set supported browsers in browserlist
* Code-splitting
  - Lazy Loading indvidual component level
    + ngx-loadable
    + lazy-af
  - Route Lazy Loading. v8 can use import syntax
  - Pre-Fetching - visible links, predictive, mouse over
  - ngx-quicklink

## Not everything needs to be a SPA
### Angular Elements
- Microsoft Sharepoint
- SPA first design

## RXJS Streams
### No subscriptions

- No ngOninit needed 
- bind in template with async pipe
- No subscribe or unsubscribe
- OnPush Change Detection
- Bound observable, will change when stream changes
- Compose Streams
- RXJS Operators
- Improve Change Detection

### Compose Stream
combineLatest, uses last emitted value to create a new stream
waits for each stream to emit at least one until emitting new value
.pipe(map(products, categories))

---

# Day2
## Angular Universal

James Daniels @jamesuriah
Engineer, Firebase
AngularFire Lead

SEO - Universal +
Percieved Loading Time
### PreRendering
loud Static Routes as array, promise and render
If lazy loading -> LAZY_MODULE_MAP

Universal should go behind CDN

Simple proxy to GCP serverless solutions

-> fast.ly

hosting -> ignore index.html
rewrite ** to run hosted universal

### Dynamic Hosting
**Cloud Run**

- stateless HTTP container
- Docker file

Spinning down to zero for when our cache misses
Don't want to pay for minimum # of servers

### Cache Control
cache control header
ETag: timestamp bust browser cache
Expires Header
Consider sending status codes

Application shells
if not server, render, else load it

## State Restoration
Check transferState and Server

Fastly.com/tutorials

github/jamesdaneils onsnapshot



## Schematics
Aaron Frost - Prettier

schematics-cli
schematics blank --name=my-component
run build

schematic for unsubscribe, prettier





### Adding Files
Templating <%= name %>

### Updating Files
Abstract Syntax Tree (AST)

[ASTExplorer.net(https://astexplorer.net)]

### Extending Schematics


### Faster Dev
Use current schematics to copy and attribute

Enforce Patterns 
Scaffolding
Consistentncy

## Better State
@kimmaida


Manage State Reactively
RxJS + Strategy

Subjects
Observables with State
multicast, next, error, complete

Service with a Subject
BehaviorSubject(initialState)
notifies subscriber on subscription, get last emit or initial value

create public observable 
store$ = this.storeSubject.asObservable() -< prevents leaky abstractions

this.data.update

state.service
.pipe(
scan() IAPOD interface , newVal IAPOD| IUPDATE
return ... iapod, ...newVal
, initialState
)

setStore(obj:IAPOD|IUPDATE)


data.service
-init returns observable, returns api call

add Stars - sets state


component init's data service 
component calls add star


### Optimisitic Updates

updates ui, before api succedds, need to handle errors seperatly

bit.ly/state-behavior

## Schematics

Collections - collection.json
Tree - staging area for changes
Tree.create, delete, exists, read

Rule, a function tht applies actions to the tree 



### CSS Grid

Bill Odom @wnodom

:host {
  display: grid;
  height: 100vh;
}

:host - grab the element i'm displaying in

:host {
  display-grid;

  grid-template-columns: repeat(5, 100px);
  grid-template-rows: repeat(5, 100px);
  grid-gap: 20px;

}

div {
  display: grid;
  place-content: center;
}

grid is not an html construct
Firefox has better dev tools for css grid

Flex is about flexing, Grid is more rigid

outline is greater than border

ng-container great for 

minmax(0, 1fr)

define entire view point,
height: 100vh,

tranform: move stuff off and on grid


## Day 3

Typescript Decorators
- provide annotations and a meta-programing

Language Feature
add functionality to classes and class members at defintion time

Property Descriptor
Object.defineProperty(cub, 'name', {value, 'Ruper'})


### NGRX Anti-Patterns

Establish patterns

- Use effects excessivly 
  - more moving parts
  - not memoized

Easy Shareability

- co locate state and component modules make sharing harder

Mapping!

- effect exhaustmap - only cares about early things you did

### CDK

Foundations for common component patterns

