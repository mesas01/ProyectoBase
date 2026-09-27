<div align="center">

# 🕊️ Legacy

### *Settle the estate, not the arguments.*
### *Liquida la herencia, no las peleas.*

**Un fondo familiar transparente para las sucesiones, construido sobre Stellar**
<br>
**A transparent family fund for estate settlements, built on Stellar**

[![Stellar](https://img.shields.io/badge/Stellar-7D00FF?style=for-the-badge&logo=stellar&logoColor=white)](https://stellar.org)
[![Soroban](https://img.shields.io/badge/Soroban-Smart%20Contracts-FF6B6B?style=for-the-badge)](https://developers.stellar.org/docs/build/smart-contracts/)
[![USDC](https://img.shields.io/badge/USDC-2775CA?style=for-the-badge)](https://www.circle.com/usdc)
[![BAF](https://img.shields.io/badge/BAF-Blockchain%20Builders%20101-000000?style=for-the-badge)](#-entregables--deliverables)

---

### 🇨🇴 [Español](#-español) • 🇺🇸 [English](#-english) • 📚 [Entregables](#-entregables--deliverables) • 👥 [Equipo](#-equipo--team)

</div>

---

## 🇨🇴 Español

### 🎯 ¿Qué es Legacy?

Cuando muere la persona que sostenía económicamente a una familia, los herederos empiezan a pagar de manera informal los gastos del hogar y de la sucesión: el predial, los servicios, la administración, la notaría, el abogado. Un mes paga la mamá, otro un hijo, otro el otro. Los recibos quedan en fotos del celular, en correos y en papeles sueltos.

Al repartir la herencia nadie sabe con certeza **quién pagó qué, cuánto se gastó ni cuánto se le debe reembolsar a cada uno**. Todo esto pasa en pleno duelo, cuando lo último que una familia quiere es discutir por plata.

**Legacy** propone un fondo familiar sobre **Stellar** donde cada aporte y cada pago queda registrado con su soporte, nadie mueve el dinero solo y, al final, el reparto se hace automáticamente según lo que le corresponde a cada heredero.

> 🧪 **Estado:** Semana 1 del programa *Blockchain Builders 101*. Estamos en la etapa de definición del problema; todavía no hay código.

### 😩 El problema hoy

| Problema | Idea de Legacy |
|----------|----------------|
| 🧾 **Recibos dispersos** en celulares, correos y papeles | Cada pago se registra con la huella digital (hash) de su factura |
| ❓ **Nadie sabe cuánto se ha gastado** ni en qué | Un registro compartido que todos los herederos pueden consultar |
| ⚖️ **Aportes desiguales** que nadie compensa | Los reembolsos pendientes se calculan solos |
| 🔒 **La plata queda en la cuenta de una persona** | Cuenta común con multifirma: nadie retira sin aprobación |
| 🧮 **Conciliación manual** al final de la sucesión | Reparto automático con un contrato Soroban |
| 💔 **Tensiones familiares** en pleno duelo | Un historial neutral que no se puede alterar |

### ⚙️ Cómo funcionaría

```mermaid
sequenceDiagram
    participant H as Heredero
    participant L as Legacy
    participant S as Stellar (fondo multifirma)
    participant C as Contrato Soroban

    H->>L: Aporta al fondo o registra un pago con su factura
    L->>S: Guarda monto, fecha, quién pagó y hash de la factura
    Note over S: Histórico inalterable y visible para todos
    H->>L: Solicita un pago desde el fondo
    L->>S: Requiere la firma de otros herederos (ej. 2 de 3)
    Note over C: Se vende un bien de la herencia
    C->>C: 1. Paga reembolsos pendientes
    C->>C: 2. Reparte según el % de cada heredero
    C->>H: USDC directo a la wallet de cada uno
```

### 🔗 ¿Por qué blockchain y no un Excel?

- **Varias partes comparten un registro:** en una herencia, cada peso reconocido a un heredero reduce lo que reciben los demás. El registro no puede depender de uno de ellos.
- **El histórico no se puede alterar:** un pago registrado en marzo no puede borrarse en diciembre, cuando se reparte.
- **Se elimina el intermediario que concentra la confianza:** nadie tiene que custodiar el dinero de los demás.

### 🛠️ Stack previsto

- **Red:** Stellar (Testnet para pruebas)
- **Contratos:** Soroban (Rust)
- **Activo:** USDC, para que el valor no fluctúe
- **Cuenta común:** multifirma nativa de Stellar
- **Privacidad:** en la red solo se guarda el hash de cada factura, nunca el documento

---

## 🇺🇸 English

### 🎯 What is Legacy?

When the person who financially supported a family passes away, the heirs start paying household and estate expenses informally: property tax, utilities, building fees, notary, lawyer. One month the mother pays, the next one of the children, then another. Receipts end up as phone photos, emails and loose papers.

When the estate is finally divided, nobody knows for sure **who paid what, how much was spent, or how much each heir should be reimbursed**. And all of this happens while grieving, when the last thing a family wants is to argue about money.

**Legacy** is a family fund on **Stellar** where every contribution and payment is recorded with its proof, nobody moves the money alone, and at the end the estate is split automatically according to each heir's share.

> 🧪 **Status:** Week 1 of the *Blockchain Builders 101* program. We are defining the problem; there is no code yet.

### 😩 The problem today

| Problem | Legacy's idea |
|---------|---------------|
| 🧾 **Scattered receipts** across phones, emails and papers | Every payment is recorded with the fingerprint (hash) of its invoice |
| ❓ **Nobody knows how much was spent** or on what | A shared record every heir can check |
| ⚖️ **Unequal contributions** nobody compensates | Pending reimbursements are calculated automatically |
| 🔒 **The money sits in one person's account** | Multisig shared account: no withdrawals without approval |
| 🧮 **Manual reconciliation** at the end of the estate process | Automatic distribution through a Soroban contract |
| 💔 **Family tension** during grief | A neutral history that cannot be altered |

### ⚙️ How it would work

```mermaid
sequenceDiagram
    participant H as Heir
    participant L as Legacy
    participant S as Stellar (multisig fund)
    participant C as Soroban contract

    H->>L: Contributes to the fund or logs a payment with its invoice
    L->>S: Stores amount, date, payer and invoice hash
    Note over S: Immutable history, visible to everyone
    H->>L: Requests a payment from the fund
    L->>S: Requires other heirs' signatures (e.g. 2 of 3)
    Note over C: An estate asset is sold
    C->>C: 1. Pays pending reimbursements
    C->>C: 2. Splits by each heir's share
    C->>H: USDC straight to each heir's wallet
```

### 🔗 Why blockchain and not a spreadsheet?

- **Several parties share one record:** in an inheritance, every peso credited to one heir reduces what the others receive. The record can't belong to any one of them.
- **History can't be altered:** a payment logged in March can't be erased in December, when the estate is split.
- **It removes the intermediary who concentrates trust:** nobody has to hold everyone else's money.

### 🛠️ Planned stack

- **Network:** Stellar (Testnet for testing)
- **Contracts:** Soroban (Rust)
- **Asset:** USDC, so the value doesn't fluctuate
- **Shared account:** Stellar native multisig
- **Privacy:** only each invoice's hash goes on-chain, never the document itself

---

## 📚 Entregables / Deliverables

| Semana / Week | Entregable / Deliverable | Enlace / Link |
|---|---|---|
| 1 | Propuestas individuales / Individual proposals | [`docs/semana1/`](docs/semana1/) |
| 1 | Problem Brief | [`docs/semana1/ProblemBrief.md`](docs/semana1/ProblemBrief.md) |
| 2–5 | _Próximamente / Coming soon_ | [`docs/`](docs/) |

---

## 👥 Equipo / Team

<div align="center">

### Santiago Mesa

<img src="FotosFounders/santiagoMesa.jpg" alt="Santiago Mesa" width="150" style="border-radius: 50%; margin: 10px;">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/santiagomesan)
[![Telegram](https://img.shields.io/badge/Telegram-2CA5E0?style=flat&logo=telegram&logoColor=white)](https://t.me/mesas01)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/mesas01)

---

### Juliana Lugo

<img src="FotosFounders/JulianaLugo.jpg" alt="Juliana Lugo" width="150" style="border-radius: 50%; margin: 10px;">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/julianalugo)
[![Telegram](https://img.shields.io/badge/Telegram-2CA5E0?style=flat&logo=telegram&logoColor=white)](https://t.me/Julilugo09)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/Julilugo09)

</div>

---

<div align="center">

### 💜 Hecho con ❤️ sobre Stellar · Made with ❤️ on Stellar

**Blockchain Acceleration Foundation — Blockchain Builders 101**

</div>
