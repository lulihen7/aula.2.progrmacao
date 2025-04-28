# aula.2.progrmacao

CREATE TABLE players (
  id SERIAL PRIMARY KEY,
  nome TEXT NOT NULL,
  tier TEXT NOT NULL,
  funcao TEXT NOT NULL,
  data_nascimento DATE,
  earnings TEXT NOT NULL
);

CREATE TABLE tempo_de_jogo (
  id SERIAL PRIMARY KEY,
  duracao_anos INT
);

CREATE TABLE campeonatos (
  id SERIAL PRIMARY KEY,
  players_id INT REFERENCES players(id) ON DELETE CASCADE,
  tempo_de_jogo_id INT REFERENCES tempo_de_jogo(id) ON DELETE CASCADE,
  nome_campeonato TEXT NOT NULL,
  colocacao INT,
  premios_ganhos TEXT
);

INSERT INTO players (nome, tier, funcao, data_nascimento, earnings)
VALUES 
('Peterbot', 'T1', 'IGL', '2007-06-20', '$571,825'),
('Cold', 'T1', 'Fragger', '2005-03-15', '$351,825'),
('Acorn', 'T1', 'Support', '2003-08-09', '$428,400'),
('Mero', 'T1', 'Fragger', '2004-07-02', '$530,000'),
('Bugha', 'T1', 'IGL', '2002-12-19', '$3,500,000'),
('Clix', 'T1', 'Fragger', '2005-01-07', '$450,000'),
('Dukez', 'T1', 'Support', '2005-09-14', '$295,000'),
('Pamstou', 'T1', 'Fragger', '2004-05-10', '$210,000'),
('Threats', 'T1', 'Support', '2006-03-11', '$320,000'),
('Setty', 'T1', 'IGL', '2003-11-18', '$600,000');


INSERT INTO tempo_de_jogo (duracao_anos)
VALUES
(5),  
(4),  
(6),  
(5),  
(6),  
(6),  
(4),  
(5),  
(4),  
(6); 

INSERT INTO campeonatos (players_id, tempo_de_jogo_id, nome_campeonato, colocacao, premios_ganhos)
VALUES
(1, 1, 'FNCS Global Championship 2023', 1, '$200,000'),
(2, 2, 'FNCS Major 2 2023', 2, '$150,000'),
(3, 3, 'FNCS All-Star Showdown', 3, '$100,000'),
(4, 4, 'FNCS Grand Finals 2022', 1, '$250,000'),
(5, 5, 'Fortnite World Cup 2019', 1, '$3,000,000'),
(6, 6, 'FNCS Invitational', 4, '$85,000'),
(7, 7, 'FNCS Grand Royale', 2, '$120,000'),
(8, 8, 'FNCS Qualifiers', 5, '$40,000'),
(9, 9, 'DreamHack Open', 3, '$60,000'),
(10, 10, 'FNCS Grand Finals 2023', 1, '$250,000');
