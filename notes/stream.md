# Stream (java 8)

## What is stream?
- we can consider Stream as a pipeline through which our collection elements passes through
- While elements passes through pipelines, it performs various operations like sorting, filtering etc.
- Useful when deals with bulk processing(can do parallel processing too)

## How stream works
- **Collection**  ===>  **create stream(step 1)** ===> **Intermediate operations(step 2)** ===> **Terminal operations (step 3)**
- At step 1: Streams are created from the data source like collection or array etc.
- At step 2: Intermediate operation like filter(), sorted(), map(),flatMap(), distinct(), peek(), limit() and skip(). are used
    - These operations transform the stream into another stream and more operations can be done top of it.
    - These are lazy in nature, means these operations get executed only when terminal operation is invoked.
- At step 3: Terminal operations like: collect(), forEach(), reduce(), count(),findFirst(),min(), max(), toArray(), findAny(),anyMatch(),  allMatch() and noneMatch() are used
  - These operations trigger the processing of the stream
  - and produce the output , means after terminal operation used, no more operation we can perform.
