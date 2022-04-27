# ProjetoFazenTECH
Trabalho FAC

CREATE DATABASE `fazenda-bd`;

CREATE TABLE `Compras` (
  `id` int(11) NOT NULL,
  `nome` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `produto` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `qtd` int(11) DEFAULT NULL,
  `dt_compra` date DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;



INSERT INTO `Compras` (`id`, `nome`, `produto`, `qtd`, `dt_compra`) VALUES
(1, 'Fazenda Esperança', 'sementes de girassol', 1000, '2020-10-09'),
(2, 'Comunidade Rural Boa Nova', 'sementes de girassol', 1500, '2020-10-14');



CREATE TABLE `Equipamentos` (
  `id` int(11) NOT NULL,
  `nome` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `tipo` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;



INSERT INTO `Equipamentos` (`id`, `nome`, `tipo`) VALUES
(1, 'colheitadeira', 'motorizado'),
(2, 'ceifadora', 'motorizado');



CREATE TABLE `Funcionarios` (
  `id` int(11) NOT NULL,
  `nome` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `cpf` varchar(11) COLLATE utf8_unicode_ci DEFAULT NULL,
  `salario` varchar(15) COLLATE utf8_unicode_ci DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;



INSERT INTO `Funcionarios` (`id`, `nome`, `cpf`, `salario`) VALUES
(1, 'Abelardo Da Silva', '53698702100', '1010'),
(2, 'Jubileu Santos', '40236902312', '1000'),
(3, 'Mariano Espindola', '43749314520', '2550'),
(4, 'Sandoval Pereira', '33793454299', '2450');



CREATE TABLE `Prod_Leite` (
  `id` int(11) NOT NULL,
  `especie` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `data_ordenha` date DEFAULT NULL,
  `temp_leite` int(11) DEFAULT NULL,
  `produtividade` int(11) DEFAULT NULL,
  `inseminacao` varchar(3) COLLATE utf8_unicode_ci DEFAULT NULL,
  `est_parto` date DEFAULT NULL,
  `secagem` date DEFAULT NULL,
  `mm_rumina` int(11) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;



INSERT INTO `Prod_Leite` (`id`, `especie`, `data_ordenha`, `temp_leite`, `produtividade`, `inseminacao`, `est_parto`, `secagem`, `mm_rumina`) VALUES
(1, 'holandesa', '2020-07-13', 32, 1800, 'nao', '2020-10-25', '2021-06-29', 3600),
(2, 'pardo suiço', '2020-05-22', 37, 2700, 'nao', '2021-01-13', '2021-09-15', 3600);



CREATE TABLE `Produtos` (
  `id` int(11) NOT NULL,
  `nome` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
  `tipo` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `qtd_estoque` int(11) DEFAULT NULL,
  `preco` float DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;



INSERT INTO `Produtos` (`id`, `nome`, `tipo`, `qtd_estoque`, `preco`) VALUES
(1, 'sementes de girassol', 'sementes', 1000, 17),
(2, 'enxada', 'material', 335, 66);



CREATE TABLE `Varejistas` (
  `id` int(11) NOT NULL,
  `nome` varchar(255) COLLATE utf8_unicode_ci DEFAULT NULL,
  `ult_compra` date DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;



INSERT INTO `Varejistas` (`id`, `nome`, `ult_compra`) VALUES
(1, 'Fazenda Esperança', '2020-06-23'),
(2, 'Comunidade Boa Nova ', '2020-08-15');


ALTER TABLE `Compras`
  ADD PRIMARY KEY (`id`);


ALTER TABLE `Equipamentos`
  ADD PRIMARY KEY (`id`);


ALTER TABLE `Funcionarios`
  ADD PRIMARY KEY (`id`);


ALTER TABLE `Prod_Leite`
  ADD PRIMARY KEY (`id`);


ALTER TABLE `Produtos`
  ADD PRIMARY KEY (`id`);


ALTER TABLE `Varejistas`
  ADD PRIMARY KEY (`id`);


ALTER TABLE `Compras`
  MODIFY `id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=3;


ALTER TABLE `Equipamentos`
  MODIFY `id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=3;


ALTER TABLE `Funcionarios`
  MODIFY `id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=5;


ALTER TABLE `Prod_Leite`
  MODIFY `id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=3;


ALTER TABLE `Produtos`
  MODIFY `id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=3;


ALTER TABLE `Varejistas`
  MODIFY `id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=3;
COMMIT;

SELECT A.nome, B.nome FROM Compras as A INNER JOIN Varejistas as B on A.nome = B.nome;

SELECT COUNT(*) FROM Funcionarios;

SELECT COUNT(DISTINCT nome) FROM Compras;

SELECT MAX(salario) FROM Funcionarios;
