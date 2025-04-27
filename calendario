const aulas = [];
const professores = {};
const alunos = {};

// Adiciona aulas ao sistema
function adicionarAula(data, aluno, professor, horas, tipo) {
    const valorHora = tipo === 'presencial' ? 80 : 50;
    const valorTotal = horas * valorHora;

    aulas.push({ data, aluno, professor, horas, tipo, valorTotal });

    // Atualizar registro do professor
    if (!professores[professor]) {
        professores[professor] = { totalReceber: 0, aulas: [] };
    }
    professores[professor].totalReceber += valorTotal;
    professores[professor].aulas.push({ data, aluno, horas, tipo });

    // Atualizar registro do aluno
    if (!alunos[aluno]) {
        alunos[aluno] = { responsavel: "Responsável Exemplo", endereco: "Endereço Exemplo", totalHoras: 0, aulas: [] };
    }
    alunos[aluno].totalHoras += horas;
    alunos[aluno].aulas.push({ data, horas });
}

// Exibir detalhes do aluno
function verAluno(nomeAluno) {
    if (!alunos[nomeAluno]) {
        alert("Aluno não encontrado!");
        return;
    }
    let info = Nome: ${nomeAluno}\nEndereço: ${alunos[nomeAluno].endereco}\nResponsável: ${alunos[nomeAluno].responsavel}\nTotal de Horas: ${alunos[nomeAluno].totalHoras}\n\nAulas:\n;
    alunos[nomeAluno].aulas.forEach(aula => {
        info += 📅 ${aula.data} - ${aula.horas} horas\n;
    });
    alert(info);
}

// Exibir detalhes do professor
function verProfessor(nomeProfessor) {
    if (!professores[nomeProfessor]) {
        alert("Professor não encontrado!");
        return;
    }
    let info = Nome: ${nomeProfessor}\nTotal a Receber: R$ ${professores[nomeProfessor].totalReceber}\n\nAulas:\n;
    professores[nomeProfessor].aulas.forEach(aula => {
        info += 📅 ${aula.data} - ${aula.horas} horas (Aluno: ${aula.aluno}, Tipo: ${aula.tipo})\n;
    });
    alert(info);
}

// Marcar professor como pago
function marcarPago(nomeProfessor) {
    if (professores[nomeProfessor]) {
        professores[nomeProfessor].totalReceber = 0;
        alert(${nomeProfessor} foi marcado como pago!);
    }
}

// Adicionar valor extra para professor
function adicionarValorExtraProfessor(nomeProfessor, valor) {
    if (professores[nomeProfessor]) {
        professores[nomeProfessor].totalReceber += valor;
        alert(R$ ${valor} adicionados ao pagamento de ${nomeProfessor}.);
    }
}

// Exemplo de uso
adicionarAula("2025-04-27", "Ana Souza", "Prof. Ricardo", 2, "presencial");
adicionarAula("2025-04-28", "Lucas Oliveira", "Prof. Ricardo", 1.5, "online");

// Atualizando valores no HTML
document.getElementById("totalRicardo").textContent = R$ ${professores["Prof. Ricardo"].totalReceber};
document.getElementById("totalMariana").textContent = R$ ${professores["Prof. Mariana"] ? professores["Prof. Mariana"].totalReceber : 0};
