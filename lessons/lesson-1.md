# Plinth introduction and features

Cardano smart contract languages can be grouped into three categories:
* Native languages that run on the Cardano node
* Compiled languages that can be compiled to a native language
* Interpreted languages that are interpreted by a compiled language.

The Cardano node can only process native languages. Currently, there are two available: simple scripts and Untyped Plutus Core (UPLC). We refer to UPLC in short Plutus. Smart contract developers do not write code directly in Plutus. Instead, they use compiled or interpreted languages that are compiled into Plutus. The language developed by [Input | Output](https://iohk.io/) that compiles to Plutus is called Plinth, previously known as PlutusTx. Plinth is a Turing-complete subset of the [Haskell](https://www.haskell.org/) programming language.

Plutus scripts can be generated using Plinth, a GHC plug-in that runs during the GHC compilation process. It modifies the program that GHC is compiling however it likes. Under the hood, though, the compilation process is more complex. The image below shows the compilation process of the on-chain validation code.

<p align="center">
  <img src="images/01-01.png" alt="Plutus compilation pipeline" width="600" />
</p>

It is wise to break down compilation pipelines by introducing intermediate languages to ensure no step is too large, and to test each step independently. For more information about the compilation process, refer to this [IO blog](https://iohk.io/en/blog/posts/2021/02/02/plutus-tx-compiling-haskell-into-plutus-core/).

There are also other compiled smart contract languages developed by companies within the Cardano ecosystem. They are all domain-specific languages (DSL) as they target the smart contract domain. For a list of those languages see the 2024 [State of the Cardano Developer Ecosystem report](https://cardano-foundation.github.io/state-of-the-developer-ecosystem/2024/#what-do-you-use-or-plan-to-use-for-writing-plutus-script-validators-smart-contracts) that shows how much these languages are used in practice by developers. Languages that compile to Plutus generate scripts that have the same logic, but might be optimized differently for factors like size or performance. 

Plinth lets developers build secure applications, forge new assets, and create smart contracts in a predictable, deterministic environment with the highest level of assurance. Furthermore, developers don't have to run a full Cardano node to test their work. The [Plutus](https://github.com/IntersectMBO/plutus) repository includes the Plinth compiler (previously called PlutusTx), enabling developers to write Haskell code that can be compiled to Plutus. The official [Plinth user guide](https://plutus.cardano.intersectmbo.org/docs/) provides developer-related information on Plutus and Plinth. 