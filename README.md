# DevOps CI/CD Presentation

## How to run

Built with [Slidev](https://github.com/slidevjs/slidev)!

To start the slide show:

- `pnpm install`
- `pnpm dev`
- visit <http://localhost:3030>

Edit the [slides.md](./slides.md) to see the changes.

Learn more about Slidev at the [documentation](https://sli.dev/).

## Why do this presentation

The goal of this presentation is to show how to use CI/CD tools to automate the testing and deployment of a web application.

The why is more important than the what. The importance of continuous intergration, automated testing and continuous deployment is not just about the tools, but about the process. It is about he DevOps principles of flow, feedback, and continuous learning. It is about the culture of collaboration and shared responsibility and how to be a good steward of a project with a community of developers.

I want to impress upon them very briefly the history of DevOps, what problem it solves, and how it is a key part of modern software development.

## Presentation outline

### Begin at the End

- Show the final product.
  - Vite application.
  - With Vitest.
  - Runs `npm build` and `npm test` on pull request.
  - Deploys to Vercel on merge to main.

### Brief Description of CI/CD

#### What is CI?

Continuous Integration is the practice of merging code changes into a shared repository frequently, ideally several times a day. Each merge triggers an automated build and test process to verify that the changes did not break the application.

#### What is CD?

Continuous Delivery or Continuous Deployment is the practice of automatically deploying code changes to a shared repository to a production environment. Continuous Delivery means that the code is always in a deployable state, but the deployment is triggered manually. Continuous Deployment means that the code is automatically deployed to production.

### What is DevOps?

DevOps refers to a set of practices that integrates software development (Dev) and IT operations (Ops) to streamline the systems development life cycle. Its primary goal is to achieve faster and more reliable delivery of high-quality software.

Beyond being a methodology, DevOps can be described as a culture or movement that fosters collaboration and communication among software developers, IT professionals, and other stakeholders involved in the software development process.

#### Brief History of DevOps

- 2006: Amazon adopts "You build it, you run it" model.
- 2009: John Allspaw and Paul Hammond presented ["10+ Deploys Per Day: Dev and Ops Cooperation at Flickr" at the Velocity Conference](https://www.youtube.com/watch?v=LdOe18KhtT4).
- 2009: First DevOpsDays conference in Ghent, Belgium.
- 2011: Gene Kim, Kevin Behr, and George Spafford published "The Phoenix Project: A Novel About IT, DevOps, and Helping Your Business Win."
- 2014: Gene Kim, Jez Humble, Patrick Debois, and John Willis published "The DevOps Handbook: How to Create World-Class Agility, Reliability, and Security in Technology Organizations."

#### Brief History of the History of DevOps

- 1980s - 1990s: Lean Manufacturing exemplified by Toyota Production System.
- 1950s - 1960s: Toyota Production System developed by Taiichi Ohno and Eiji Toyoda with help of W. Edwards Deming.
- 1920s - 1930s: Statistical Process Control developed by Walter Shewhart and W. Edwards Deming.

#### The Three Ways

- The First Way: Flow
- The Second Way: Feedback
- The Third Way: Continuous Learning and Improvement

### Continuous Integration (CI)

#### Why CI?

#### Benefits of CI

- Catch bugs early because you are frequently testing and can realize you are breaking something.
- Reduce integration problems because you are integrating frequently and conflicts are smaller and easier to resolve.
- Improve code quality because you are writing testable code and running these tests frequently.
- Increase developer confidence because you are getting feedback quickly on the the health of the entire application.
- Better collaboration because coworkers are not stepping on each other's toes with huge changes generating conflicts.

#### Costs of CI

- Time to set up the CI pipeline.
- Time to create and maintain tests.
- Learning curve.
- Bad feedback. If tests failures are false positives or run too slowly, they defeat the purpose of CI.

#### How to do CI?

### Continuous Delivery/Deployment (CD)

#### Why CD?

#### Benefits of CD

- Faster time to market because you are deploying frequently.
- Lower risk because you are deploying smaller changes.
- Streamlined feedback loop because you are getting feedback from users quickly.
- Clear traceability because you are deploying from a well defined set of changes
- Confidence that your code is always in a deployable state.

#### Costs of CD

- Time to set up the CD pipeline.
- Time to maintain the CD pipeline.
- If you are not confident in your CI process, you will likely will be introducing bugs into production quickly.
