# projeto4-modelagem-de-um-pequeno-sistema-com-uml-e-bpmn

modelo criado

    classDiagram
    class Sala {
        - id: int
        - nome: string
        - capacidade: int
        + verificarDisponibilidade(): bool
    }

    class Usuario {
        - id: int
        - nome: string
        - email: string
        + cadastrar(): void
        + cancelarReserva(): void
    }

    class Reserva {
        - id: int
        - data: Date
        - horaInicio: Time
        - horaFim: Time
        - status: string
        + confirmar(): void
        + cancelar(): void
    }

    Sala "1" --> "N" Reserva : possui
    Usuario "1" --> "N" Reserva : faz

    graph TD;
    A[Início] --> B[Usuário acessa o sistema]
    B --> C[Seleciona a Sala]
    C --> D[Escolhe data e horário]
    D --> E[Verifica disponibilidade]
    E -- Disponível --> F[Confirma reserva]
    E -- Não disponível --> C
    F --> G[Reserva registrada]
    G --> H[Fim]

