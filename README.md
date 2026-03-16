
# How has an increase in the number of women lawmakers impacted gender equality in Africa?

The number of female representatives has increased since 2000 in parliaments across Africa. Has this positively changed the lives of women?

<i>Idea, data analysis and visualization: Ana Muñoz Padrós</i>

<i>Interviews: Facilited by Jean-Michel Bos and conducted by Ana Muñoz Padrós</i>

<i>Contribution to reporting: Jean-Michel Bos</i>

<i>Writing: Ana Muñoz Padrós</i>

<i>Editing: Gianna-Carina Grün, Dirke Köpp, Milan Gagnon</i>

Read the full articles on DW.com: <a href='https://www.dw.com/en/more-women-sit-in-african-parliaments-but-equality-eludes/a-76291235'>English</a>


# Definition of parameters

## Countries

The selection of African countries has followed the <a href='https://unstats.un.org/unsd/methodology/m49/overview/'> UNSD overview.</a>

## Gender equality markers

Data from all markers has been collected from the <a href='https://www.worldbank.org/ext/en/home'>World Bank group</a>, as well as trusted sources used by the World Bank, including International IDEA and Demographic and Health Surveys (DHS)

### Parliament quotas

Women in parliaments are the percentage of parliamentary seats in a single or lower chamber held by women.

We have followed the definitions and categorisations of gender quotas established by <a href='https://www.idea.int/'>International IDEA</a>:

- Legislated Candidate Quotas: This quota provision reserves a number of places on electoral lists for female candidates. 

- Reserved seats: Reserves a number of seats in a legislated assembly for women. 

- Voluntary Political Party Quota: These are rules or targets set by political parties to include a certain percentage of women as election candidates. This does not include quotas for internal party structures. 

### Other markers

Following our hypothesis, we set out our analysis to find correlations between the number of women in parliament and different gender equality markers. These were selected from United Nations SDG 4 (education) and SDG 5 (gender equality). They can be grouped into three axes: education, financial independence, and sexual and bodily autonomy. 

- 'youth literacy': Gender parity index for youth literacy rate is the ratio of females to males ages 15-24 who can both read and write with understanding a short simple statement about their everyday life.  

- 'family planning' or contraception represents the demand for family planning satisfied (% of married women with demand for family planning)

- 'belief beating' represents the percentage of women ages 15-49 who believe a husband/partner is justified in hitting or beating his wife/partner for any reason

- The indicator 'refuse sex' measures the percentage of women aged 15-49 who believe that a wife is justified in refusing to have sex with her husband.

- 'savings' is the percentage of respondents aged 15+ who report saving or setting aside any money at a bank or another type of financial institution in the past year

- 'landowner' is the proportion of women ages 15-49 or men who own land (either alone, jointly, both alone and jointly).

Some parameters were pre-selected and eventually discarded from the reporting, either because they were boolean values (true/false), or because the most recent data was over seven years old. The discarded categories were: access to abortion, right to divorce, belief that FGM should end, gender violence, women can be head of households, female sole owners. 

# Methodology

The main analyses have been the calculation of averages and medians across time and countries, and the calculation of correlations.

We have chosen to calculate the median, the middle value in a dataset, to avoid the interference of outliers, in the cases where there the dataset presented extreme values.

## Correlations

A correlation is a statistical relationship between two random variables. Correlation doesn't imply causation or dependency. 

We have used <a href='https://www.britannica.com/topic/Pearsons-correlation-coefficient'>Pearson's correlation coefficient</a> and compared subsets of at least three values each, by calling .corr() in pandas (see the complete code in the REPO_correlationAll.ipynb notebook).

We have considered correlation coefficients of >0.7 and <-0.7 indicative of "strong correlations", as stated by various expert sources, including ScienceDirect and the University of Southampton.

These are the pairs of variables which had an absolute correlation value of 0.7 or over. Absolute values include positive and negative values. 

<table>
  <td><b>Marker 1</b></td>
  <td><b>Marker 2</b></td>
  <td><b>Countries</b></td>
  <tr>
    <td><b>Parliament</b></td>
    <td>Savings</td>
    <td>14</td>
  </tr>
    <tr>
    <td>Parliament</td>
    <td>belief beating</td>
    <td>11</td>
  </tr>
  <tr>
    <td>Parliament</td>
    <td>family planning</td>
    <td>11</td>
  </tr>
  <tr>
    <td>Parliament</td>
    <td>refuse sex</td>
    <td>8</td>
  </tr>
  <tr>
    <td>Parliament</td>
    <td>youth literacy</td>
    <td>21</td>
  </tr>
  <tr>
    <td><b>Savings</b></td>
    <td>belief beating</td>
    <td>1</td>
  </tr>
  <tr>
    <td>Savings</td>
    <td>family planning</td>
    <td>1</td>
  </tr>
  </tr>
  <tr>
    <td>Savings</td>
    <td>landowner</td>
    <td>1</td>
  </tr>
    <tr>
    <td>Savings</td>
    <td>refuse sex</td>
    <td>1</td>
  </tr>
    <tr>
    <td>Savings</td>
    <td>youth literacy</td>
    <td>1</td>
  </tr>
  <tr>
    <td><b>belief beating</b></td>
    <td>family planning</td>
    <td>14</td>
  </tr>
  <tr>
    <td>belief beating</td>
    <td>landowner</td>
    <td>1</td>
  </tr>
  <tr>
    <td>belief beating</td>
    <td>refuse sex</td>
    <td>6</td>
  </tr>
  <tr>
    <td>belief beating</td>
    <td>youth literacy</td>
    <td>4</td>
  </tr>
  <tr>
    <td><b>family planning</b></td>
    <td>refuse sex</td>
    <td>6</td>
  </tr>
  <tr>
    <td>family planning</td>
    <td>landowner</td>
    <td>2</td>
  </tr>
  <tr>
    <td>family planning</td>
    <td>youth literacy</td>
    <td>7</td>
  </tr>
  <tr>
    <td><b>landowner</b></td>
    <td>refuse sex</td>
    <td>1</td>
  </tr>
  <tr>
    <td>landowner</td>
    <td>youth literacy</td>
    <td>2</td>
  </tr>
  <tr>
    <td><b>refuse sex</b></td>
    <td>youth literacy</td>
    <td>3</td>
  </tr>
</table>

Following these results, we took a closer look at the parliament - youth education pair:

<table>
  <thead>
    <tr>
      <th>Marker 1</th>
      <th>Marker 2</th>
      <th>correlation</th>
      <th>country</th>
      <th>n_years</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Parliament</td>
      <td>youth literacy</td>
      <td>0.753969</td>
      <td>Algeria</td>
      <td>5</td>
    </tr>
    <tr>
      <td>Parliament</td>
      <td>youth literacy</td>
      <td>0.727851</td>
      <td>Angola</td>
      <td>3</td>
    </tr>
    <tr>
      <td>Parliament</td>
      <td>youth literacy</td>
      <td>0.842234</td>
      <td>Cameroon</td>
      <td>7</td>
    </tr>
    <tr>
      <td>Parliament</td>
      <td>youth literacy</td>
      <td>0.711675</td>
      <td>Congo, Dem. Rep.</td>
      <td>5</td>
    </tr>
    <tr>
      <td>Parliament</td>
      <td>youth literacy</td>
      <td>0.813054</td>
      <td>Egypt, Arab Rep.</td>
      <td>6</td>
    </tr>
    <tr>
      <td>Parliament</td>
      <td>youth literacy</td>
      <td>0.719760</td>
      <td>Ethiopia</td>
      <td>7</td>
    </tr>
    <tr>
      <td>Parliament</td>
      <td>youth literacy</td>
      <td>0.819510</td>
      <td>Gambia, The</td>
      <td>4</td>
    </tr>
    <tr>
      <td>Parliament</td>
      <td>youth literacy</td>
      <td>0.759066</td>
      <td>Guinea</td>
      <td>4</td>
    </tr>
    <tr>
      <td>Parliament</td>
      <td>youth literacy</td>
      <td>0.795931</td>
      <td>Guinea-Bissau</td>
      <td>3</td>
    </tr>
    <tr>
      <td>Parliament</td>
      <td>youth literacy</td>
      <td>0.822638</td>
      <td>Kenya</td>
      <td>4</td>
    </tr>
    <tr>
      <td>Parliament</td>
      <td>youth literacy</td>
      <td>0.879705</td>
      <td>Morocco</td>
      <td>6</td>
    </tr>
    <tr>
      <td>Parliament</td>
      <td>youth literacy</td>
      <td>0.787982</td>
      <td>Mozambique</td>
      <td>5</td>
    </tr>
    <tr>
      <td>Parliament</td>
      <td>youth literacy</td>
      <td>0.772167</td>
      <td>Senegal</td>
      <td>10</td>
    </tr>
    <tr>
      <td>Parliament</td>
      <td>youth literacy</td>
      <td>0.779991</td>
      <td>Tanzania</td>
      <td>4</td>
    </tr>
    <tr>
      <td>Parliament</td>
      <td>youth literacy</td>
      <td>0.754915</td>
      <td>Tunisia</td>
      <td>9</td>
    </tr>
    <tr>
      <td>Parliament</td>
      <td>youth literacy</td>
      <td>0.822892</td>
      <td>Uganda</td>
      <td>6</td>
    </tr>
    <tr>
      <td>Parliament</td>
      <td>youth literacy</td>
      <td>0.796708</td>
      <td>Zimbabwe</td>
      <td>4</td>
    </tr>
  </tbody>
</table>

## Other methodological notes

### Including disaggregated data points

In the cases of 'Women who believe a wife is justified refusing sex with her husband', 'Women who believe a husband is justified in beating his wife', and land ownership datasets, where the total values were broken down in second-level categories in the column COMP_BREAKDOWN_2_LABEL (e.g. by type of ownership or reasons for justification), we have calculated and considered the mean among all values per year and country. 

### Other parameters' charts
Dot ranges visuals show the change in different gender equality indicators across African countries. 

Some countries are not represented because a single data point was available, preventing comparison. They are:

<b>Domestic violence:</b> Morocco, Tunisia, Niger, South Africa, Benin, Lesotho, Botswana, Sudan, Eswatini, Guinea, South Sudan

<b>Savings:</b> Djibouti, Libya, Somalia

<b>Female youth literacy:</b> Somalia and South Sudan

<b>Belief wife-beating:</b> South Africa, Eswatini, Angola, Mauritania, Togo, Comoros, Morocco, Eritrea, Chad

<b>Belief refuse sex</b>: Sao Tome and Principe, Togo, Mauritania, Congo, Angola, Cote d'Ivoire, Morocco, Chad, Comoros, Eswatini

<b>Access to family planning:</b> Morocco, South Africa, Eswatini, Gabon, Sao Tome and Principe, Cote d'Ivoire, Comoros, Togo, Angola, Eritrea

<b>Land ownwership:</b> Burkina Faso, Cameroon, Chad, Comoros, DR Congo, Congo, Cote d'Ivoire, Egypt, Ghana, Lesotho, Liberia, Madagascar, Malawi, Mauritania, Namibia, Niger, Tanzania, Togo
