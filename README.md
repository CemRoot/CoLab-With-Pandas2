# CoLab-With-Pandas2
Learn Data Exploration with Pandas by Analysing the Post-University Salaries of Graduates by Major


{
  "nbformat": 4,
  "nbformat_minor": 0,
  "metadata": {
    "colab": {
      "provenance": [],
      "toc_visible": true,
      "include_colab_link": true
    },
    "kernelspec": {
      "name": "python3",
      "display_name": "Python 3"
    }
  },
  "cells": [
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "view-in-github",
        "colab_type": "text"
      },
      "source": [
        "<a href=\"https://colab.research.google.com/github/CemRoot/CoLab-With-Pandas2/blob/main/Data_Exploration_Pandas_College_Major_(complete).ipynb\" target=\"_parent\"><img src=\"https://colab.research.google.com/assets/colab-badge.svg\" alt=\"Open In Colab\"/></a>"
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "uJ5KYjiPV5Ul"
      },
      "source": [
        "## Upload the Data and Read the .csv File"
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "PNqLi9vgJh97"
      },
      "source": [
        "import pandas as pd"
      ],
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "FLXFmF4tbobK"
      },
      "source": [
        "df = pd.read_csv('salaries_by_college_major.csv')"
      ],
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "sHIcvGzlbuVR",
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 237
        },
        "outputId": "14714f37-a000-4562-fb9a-8c96f9af3b20"
      },
      "source": [
        "df.head()"
      ],
      "execution_count": null,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/html": [
              "<div>\n",
              "<style scoped>\n",
              "    .dataframe tbody tr th:only-of-type {\n",
              "        vertical-align: middle;\n",
              "    }\n",
              "\n",
              "    .dataframe tbody tr th {\n",
              "        vertical-align: top;\n",
              "    }\n",
              "\n",
              "    .dataframe thead th {\n",
              "        text-align: right;\n",
              "    }\n",
              "</style>\n",
              "<table border=\"1\" class=\"dataframe\">\n",
              "  <thead>\n",
              "    <tr style=\"text-align: right;\">\n",
              "      <th></th>\n",
              "      <th>Undergraduate Major</th>\n",
              "      <th>Starting Median Salary</th>\n",
              "      <th>Mid-Career Median Salary</th>\n",
              "      <th>Mid-Career 10th Percentile Salary</th>\n",
              "      <th>Mid-Career 90th Percentile Salary</th>\n",
              "      <th>Group</th>\n",
              "    </tr>\n",
              "  </thead>\n",
              "  <tbody>\n",
              "    <tr>\n",
              "      <th>0</th>\n",
              "      <td>Accounting</td>\n",
              "      <td>46000.0</td>\n",
              "      <td>77100.0</td>\n",
              "      <td>42200.0</td>\n",
              "      <td>152000.0</td>\n",
              "      <td>Business</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>1</th>\n",
              "      <td>Aerospace Engineering</td>\n",
              "      <td>57700.0</td>\n",
              "      <td>101000.0</td>\n",
              "      <td>64300.0</td>\n",
              "      <td>161000.0</td>\n",
              "      <td>STEM</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>2</th>\n",
              "      <td>Agriculture</td>\n",
              "      <td>42600.0</td>\n",
              "      <td>71900.0</td>\n",
              "      <td>36300.0</td>\n",
              "      <td>150000.0</td>\n",
              "      <td>Business</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>3</th>\n",
              "      <td>Anthropology</td>\n",
              "      <td>36800.0</td>\n",
              "      <td>61500.0</td>\n",
              "      <td>33800.0</td>\n",
              "      <td>138000.0</td>\n",
              "      <td>HASS</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>4</th>\n",
              "      <td>Architecture</td>\n",
              "      <td>41600.0</td>\n",
              "      <td>76800.0</td>\n",
              "      <td>50600.0</td>\n",
              "      <td>136000.0</td>\n",
              "      <td>Business</td>\n",
              "    </tr>\n",
              "  </tbody>\n",
              "</table>\n",
              "</div>"
            ],
            "text/plain": [
              "     Undergraduate Major  ...     Group\n",
              "0             Accounting  ...  Business\n",
              "1  Aerospace Engineering  ...      STEM\n",
              "2            Agriculture  ...  Business\n",
              "3           Anthropology  ...      HASS\n",
              "4           Architecture  ...  Business\n",
              "\n",
              "[5 rows x 6 columns]"
            ]
          },
          "metadata": {
            "tags": []
          },
          "execution_count": 3
        }
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "KH2jLKmvWB0r"
      },
      "source": [
        "# Data Exploration and Data Cleaning"
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "HngjSfIXfXZ-",
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "outputId": "1a5c94fe-989b-444e-9a59-f793bed061e1"
      },
      "source": [
        "df.shape"
      ],
      "execution_count": null,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/plain": [
              "(51, 6)"
            ]
          },
          "metadata": {
            "tags": []
          },
          "execution_count": 4
        }
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "nbHfTGssi5dr",
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "outputId": "a969def2-27d9-4e01-e26b-ae6b5b4d810a"
      },
      "source": [
        "df.columns"
      ],
      "execution_count": null,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/plain": [
              "Index(['Undergraduate Major', 'Starting Median Salary',\n",
              "       'Mid-Career Median Salary', 'Mid-Career 10th Percentile Salary',\n",
              "       'Mid-Career 90th Percentile Salary', 'Group'],\n",
              "      dtype='object')"
            ]
          },
          "metadata": {
            "tags": []
          },
          "execution_count": 5
        }
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "Lwc7l1ZsjXkt",
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 1000
        },
        "outputId": "72facfe5-0297-48c5-f21e-35c45b179967"
      },
      "source": [
        "df.isna()"
      ],
      "execution_count": null,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/html": [
              "<div>\n",
              "<style scoped>\n",
              "    .dataframe tbody tr th:only-of-type {\n",
              "        vertical-align: middle;\n",
              "    }\n",
              "\n",
              "    .dataframe tbody tr th {\n",
              "        vertical-align: top;\n",
              "    }\n",
              "\n",
              "    .dataframe thead th {\n",
              "        text-align: right;\n",
              "    }\n",
              "</style>\n",
              "<table border=\"1\" class=\"dataframe\">\n",
              "  <thead>\n",
              "    <tr style=\"text-align: right;\">\n",
              "      <th></th>\n",
              "      <th>Undergraduate Major</th>\n",
              "      <th>Starting Median Salary</th>\n",
              "      <th>Mid-Career Median Salary</th>\n",
              "      <th>Mid-Career 10th Percentile Salary</th>\n",
              "      <th>Mid-Career 90th Percentile Salary</th>\n",
              "      <th>Group</th>\n",
              "    </tr>\n",
              "  </thead>\n",
              "  <tbody>\n",
              "    <tr>\n",
              "      <th>0</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>1</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>2</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>3</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>4</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>5</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>6</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>7</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>8</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>9</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>10</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>11</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>12</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>13</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>14</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>15</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>16</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>17</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>18</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>19</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>20</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>21</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>22</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>23</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>24</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>25</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>26</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>27</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>28</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>29</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>30</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>31</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>32</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>33</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>34</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>35</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>36</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>37</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>38</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>39</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>40</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>41</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>42</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>43</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>44</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>45</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>46</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>47</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>48</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>49</th>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "      <td>False</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>50</th>\n",
              "      <td>False</td>\n",
              "      <td>True</td>\n",
              "      <td>True</td>\n",
              "      <td>True</td>\n",
              "      <td>True</td>\n",
              "      <td>True</td>\n",
              "    </tr>\n",
              "  </tbody>\n",
              "</table>\n",
              "</div>"
            ],
            "text/plain": [
              "    Undergraduate Major  ...  Group\n",
              "0                 False  ...  False\n",
              "1                 False  ...  False\n",
              "2                 False  ...  False\n",
              "3                 False  ...  False\n",
              "4                 False  ...  False\n",
              "5                 False  ...  False\n",
              "6                 False  ...  False\n",
              "7                 False  ...  False\n",
              "8                 False  ...  False\n",
              "9                 False  ...  False\n",
              "10                False  ...  False\n",
              "11                False  ...  False\n",
              "12                False  ...  False\n",
              "13                False  ...  False\n",
              "14                False  ...  False\n",
              "15                False  ...  False\n",
              "16                False  ...  False\n",
              "17                False  ...  False\n",
              "18                False  ...  False\n",
              "19                False  ...  False\n",
              "20                False  ...  False\n",
              "21                False  ...  False\n",
              "22                False  ...  False\n",
              "23                False  ...  False\n",
              "24                False  ...  False\n",
              "25                False  ...  False\n",
              "26                False  ...  False\n",
              "27                False  ...  False\n",
              "28                False  ...  False\n",
              "29                False  ...  False\n",
              "30                False  ...  False\n",
              "31                False  ...  False\n",
              "32                False  ...  False\n",
              "33                False  ...  False\n",
              "34                False  ...  False\n",
              "35                False  ...  False\n",
              "36                False  ...  False\n",
              "37                False  ...  False\n",
              "38                False  ...  False\n",
              "39                False  ...  False\n",
              "40                False  ...  False\n",
              "41                False  ...  False\n",
              "42                False  ...  False\n",
              "43                False  ...  False\n",
              "44                False  ...  False\n",
              "45                False  ...  False\n",
              "46                False  ...  False\n",
              "47                False  ...  False\n",
              "48                False  ...  False\n",
              "49                False  ...  False\n",
              "50                False  ...   True\n",
              "\n",
              "[51 rows x 6 columns]"
            ]
          },
          "metadata": {
            "tags": []
          },
          "execution_count": 6
        }
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "gOxwMshdk207",
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 237
        },
        "outputId": "02de10d7-770a-4fd6-bab2-3ddd66a97862"
      },
      "source": [
        "df.tail()"
      ],
      "execution_count": null,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/html": [
              "<div>\n",
              "<style scoped>\n",
              "    .dataframe tbody tr th:only-of-type {\n",
              "        vertical-align: middle;\n",
              "    }\n",
              "\n",
              "    .dataframe tbody tr th {\n",
              "        vertical-align: top;\n",
              "    }\n",
              "\n",
              "    .dataframe thead th {\n",
              "        text-align: right;\n",
              "    }\n",
              "</style>\n",
              "<table border=\"1\" class=\"dataframe\">\n",
              "  <thead>\n",
              "    <tr style=\"text-align: right;\">\n",
              "      <th></th>\n",
              "      <th>Undergraduate Major</th>\n",
              "      <th>Starting Median Salary</th>\n",
              "      <th>Mid-Career Median Salary</th>\n",
              "      <th>Mid-Career 10th Percentile Salary</th>\n",
              "      <th>Mid-Career 90th Percentile Salary</th>\n",
              "      <th>Group</th>\n",
              "    </tr>\n",
              "  </thead>\n",
              "  <tbody>\n",
              "    <tr>\n",
              "      <th>46</th>\n",
              "      <td>Psychology</td>\n",
              "      <td>35900.0</td>\n",
              "      <td>60400.0</td>\n",
              "      <td>31600.0</td>\n",
              "      <td>127000.0</td>\n",
              "      <td>HASS</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>47</th>\n",
              "      <td>Religion</td>\n",
              "      <td>34100.0</td>\n",
              "      <td>52000.0</td>\n",
              "      <td>29700.0</td>\n",
              "      <td>96400.0</td>\n",
              "      <td>HASS</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>48</th>\n",
              "      <td>Sociology</td>\n",
              "      <td>36500.0</td>\n",
              "      <td>58200.0</td>\n",
              "      <td>30700.0</td>\n",
              "      <td>118000.0</td>\n",
              "      <td>HASS</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>49</th>\n",
              "      <td>Spanish</td>\n",
              "      <td>34000.0</td>\n",
              "      <td>53100.0</td>\n",
              "      <td>31000.0</td>\n",
              "      <td>96400.0</td>\n",
              "      <td>HASS</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>50</th>\n",
              "      <td>Source: PayScale Inc.</td>\n",
              "      <td>NaN</td>\n",
              "      <td>NaN</td>\n",
              "      <td>NaN</td>\n",
              "      <td>NaN</td>\n",
              "      <td>NaN</td>\n",
              "    </tr>\n",
              "  </tbody>\n",
              "</table>\n",
              "</div>"
            ],
            "text/plain": [
              "      Undergraduate Major  ...  Group\n",
              "46             Psychology  ...   HASS\n",
              "47               Religion  ...   HASS\n",
              "48              Sociology  ...   HASS\n",
              "49                Spanish  ...   HASS\n",
              "50  Source: PayScale Inc.  ...    NaN\n",
              "\n",
              "[5 rows x 6 columns]"
            ]
          },
          "metadata": {
            "tags": []
          },
          "execution_count": 7
        }
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "ag1fbMC0ltur",
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 219
        },
        "outputId": "ddf82680-ca3e-42a0-9fd1-36d49726789e"
      },
      "source": [
        "clean_df = df.dropna()\n",
        "clean_df.tail()"
      ],
      "execution_count": null,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/html": [
              "<div>\n",
              "<style scoped>\n",
              "    .dataframe tbody tr th:only-of-type {\n",
              "        vertical-align: middle;\n",
              "    }\n",
              "\n",
              "    .dataframe tbody tr th {\n",
              "        vertical-align: top;\n",
              "    }\n",
              "\n",
              "    .dataframe thead th {\n",
              "        text-align: right;\n",
              "    }\n",
              "</style>\n",
              "<table border=\"1\" class=\"dataframe\">\n",
              "  <thead>\n",
              "    <tr style=\"text-align: right;\">\n",
              "      <th></th>\n",
              "      <th>Undergraduate Major</th>\n",
              "      <th>Starting Median Salary</th>\n",
              "      <th>Mid-Career Median Salary</th>\n",
              "      <th>Mid-Career 10th Percentile Salary</th>\n",
              "      <th>Mid-Career 90th Percentile Salary</th>\n",
              "      <th>Group</th>\n",
              "    </tr>\n",
              "  </thead>\n",
              "  <tbody>\n",
              "    <tr>\n",
              "      <th>45</th>\n",
              "      <td>Political Science</td>\n",
              "      <td>40800.0</td>\n",
              "      <td>78200.0</td>\n",
              "      <td>41200.0</td>\n",
              "      <td>168000.0</td>\n",
              "      <td>HASS</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>46</th>\n",
              "      <td>Psychology</td>\n",
              "      <td>35900.0</td>\n",
              "      <td>60400.0</td>\n",
              "      <td>31600.0</td>\n",
              "      <td>127000.0</td>\n",
              "      <td>HASS</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>47</th>\n",
              "      <td>Religion</td>\n",
              "      <td>34100.0</td>\n",
              "      <td>52000.0</td>\n",
              "      <td>29700.0</td>\n",
              "      <td>96400.0</td>\n",
              "      <td>HASS</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>48</th>\n",
              "      <td>Sociology</td>\n",
              "      <td>36500.0</td>\n",
              "      <td>58200.0</td>\n",
              "      <td>30700.0</td>\n",
              "      <td>118000.0</td>\n",
              "      <td>HASS</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>49</th>\n",
              "      <td>Spanish</td>\n",
              "      <td>34000.0</td>\n",
              "      <td>53100.0</td>\n",
              "      <td>31000.0</td>\n",
              "      <td>96400.0</td>\n",
              "      <td>HASS</td>\n",
              "    </tr>\n",
              "  </tbody>\n",
              "</table>\n",
              "</div>"
            ],
            "text/plain": [
              "   Undergraduate Major  ...  Group\n",
              "45   Political Science  ...   HASS\n",
              "46          Psychology  ...   HASS\n",
              "47            Religion  ...   HASS\n",
              "48           Sociology  ...   HASS\n",
              "49             Spanish  ...   HASS\n",
              "\n",
              "[5 rows x 6 columns]"
            ]
          },
          "metadata": {
            "tags": []
          },
          "execution_count": 8
        }
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "oaKtSQloWVC2"
      },
      "source": [
        "# Accessing Columns and Individual Cells"
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "jmG-K0HPnrO3",
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "outputId": "79a9500b-26a8-430f-dcd1-3ec77e6091c8"
      },
      "source": [
        "clean_df['Starting Median Salary'].max()"
      ],
      "execution_count": null,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/plain": [
              "74300.0"
            ]
          },
          "metadata": {
            "tags": []
          },
          "execution_count": 9
        }
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "PAoOp9r8nsKo",
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "outputId": "de404d22-62d1-43d8-a3d0-018ef81d2a22"
      },
      "source": [
        "clean_df['Starting Median Salary'].idxmax()"
      ],
      "execution_count": null,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/plain": [
              "43"
            ]
          },
          "metadata": {
            "tags": []
          },
          "execution_count": 10
        }
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "MzEgHdhZodAq",
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "outputId": "57cee6bb-dff0-407f-87a7-a020e7736261"
      },
      "source": [
        "clean_df['Starting Median Salary'][43]"
      ],
      "execution_count": null,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/plain": [
              "74300.0"
            ]
          },
          "metadata": {
            "tags": []
          },
          "execution_count": 11
        }
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "A8RqDxtto48F",
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 35
        },
        "outputId": "b2bd670b-1cf5-4798-8af6-92b55c365c57"
      },
      "source": [
        "clean_df['Undergraduate Major'].loc[43]"
      ],
      "execution_count": null,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "application/vnd.google.colaboratory.intrinsic+json": {
              "type": "string"
            },
            "text/plain": [
              "'Physician Assistant'"
            ]
          },
          "metadata": {
            "tags": []
          },
          "execution_count": 12
        }
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "CPXcE9mRpFnL",
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 35
        },
        "outputId": "e5d46bbf-5ca8-416a-a4c5-444d07b3dc1c"
      },
      "source": [
        "clean_df['Undergraduate Major'][43]"
      ],
      "execution_count": null,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "application/vnd.google.colaboratory.intrinsic+json": {
              "type": "string"
            },
            "text/plain": [
              "'Physician Assistant'"
            ]
          },
          "metadata": {
            "tags": []
          },
          "execution_count": 13
        }
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "Se2YRmsypgqw",
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "outputId": "3a9fdf24-40d8-4be2-e499-abfced6a8174"
      },
      "source": [
        "clean_df.loc[43]"
      ],
      "execution_count": null,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/plain": [
              "Undergraduate Major                  Physician Assistant\n",
              "Starting Median Salary                             74300\n",
              "Mid-Career Median Salary                           91700\n",
              "Mid-Career 10th Percentile Salary                  66400\n",
              "Mid-Career 90th Percentile Salary                 124000\n",
              "Group                                               STEM\n",
              "Name: 43, dtype: object"
            ]
          },
          "metadata": {
            "tags": []
          },
          "execution_count": 14
        }
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "18_KA7l7WfDh"
      },
      "source": [
        "# Solution: Highest and Lowest Earning Degrees"
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "_EvDORASpjDu",
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 70
        },
        "outputId": "28f4bb3b-bb6b-4181-c114-5d38584d4015"
      },
      "source": [
        "print(clean_df['Mid-Career Median Salary'].max())\n",
        "print(f\"Index for the max mid career salary: {clean_df['Mid-Career Median Salary'].idxmax()}\")\n",
        "clean_df['Undergraduate Major'][8]"
      ],
      "execution_count": null,
      "outputs": [
        {
          "output_type": "stream",
          "text": [
            "107000.0\n",
            "Index for the max mid career salary: 8\n"
          ],
          "name": "stdout"
        },
        {
          "output_type": "execute_result",
          "data": {
            "application/vnd.google.colaboratory.intrinsic+json": {
              "type": "string"
            },
            "text/plain": [
              "'Chemical Engineering'"
            ]
          },
          "metadata": {
            "tags": []
          },
          "execution_count": 15
        }
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "dQGN8gZntL2V",
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 53
        },
        "outputId": "de1d812a-129e-4ebd-9f27-a87ffc8b51b5"
      },
      "source": [
        "print(clean_df['Starting Median Salary'].min())\n",
        "clean_df['Undergraduate Major'].loc[clean_df['Starting Median Salary'].idxmin()]"
      ],
      "execution_count": null,
      "outputs": [
        {
          "output_type": "stream",
          "text": [
            "34000.0\n"
          ],
          "name": "stdout"
        },
        {
          "output_type": "execute_result",
          "data": {
            "application/vnd.google.colaboratory.intrinsic+json": {
              "type": "string"
            },
            "text/plain": [
              "'Spanish'"
            ]
          },
          "metadata": {
            "tags": []
          },
          "execution_count": 16
        }
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "Z0rvJWSdtNN5",
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "outputId": "8bac1794-a54a-40ff-992a-a3051cc5d60e"
      },
      "source": [
        "clean_df.loc[clean_df['Mid-Career Median Salary'].idxmin()]"
      ],
      "execution_count": null,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/plain": [
              "Undergraduate Major                  Education\n",
              "Starting Median Salary                   34900\n",
              "Mid-Career Median Salary                 52000\n",
              "Mid-Career 10th Percentile Salary        29300\n",
              "Mid-Career 90th Percentile Salary       102000\n",
              "Group                                     HASS\n",
              "Name: 18, dtype: object"
            ]
          },
          "metadata": {
            "tags": []
          },
          "execution_count": 17
        }
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "cd_pPQo7Wkxi"
      },
      "source": [
        "# Sorting Values & Adding Columns: Majors with the Most Potential vs Lowest Risk"
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "Pqw8VPbEtpcR",
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 254
        },
        "outputId": "a20724d5-4705-4925-b41d-fa778690b358"
      },
      "source": [
        "# clean_df['Mid-Career 90th Percentile Salary'] - clean_df['Mid-Career 10th Percentile Salary']\n",
        "# clean_df['Mid-Career 90th Percentile Salary'].subtract(clean_df['Mid-Career 10th Percentile Salary'])\n",
        "spread_col = clean_df['Mid-Career 90th Percentile Salary'] - clean_df['Mid-Career 10th Percentile Salary']\n",
        "clean_df.insert(1, 'Spread', spread_col)\n",
        "clean_df.head()"
      ],
      "execution_count": null,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/html": [
              "<div>\n",
              "<style scoped>\n",
              "    .dataframe tbody tr th:only-of-type {\n",
              "        vertical-align: middle;\n",
              "    }\n",
              "\n",
              "    .dataframe tbody tr th {\n",
              "        vertical-align: top;\n",
              "    }\n",
              "\n",
              "    .dataframe thead th {\n",
              "        text-align: right;\n",
              "    }\n",
              "</style>\n",
              "<table border=\"1\" class=\"dataframe\">\n",
              "  <thead>\n",
              "    <tr style=\"text-align: right;\">\n",
              "      <th></th>\n",
              "      <th>Undergraduate Major</th>\n",
              "      <th>Spread</th>\n",
              "      <th>Starting Median Salary</th>\n",
              "      <th>Mid-Career Median Salary</th>\n",
              "      <th>Mid-Career 10th Percentile Salary</th>\n",
              "      <th>Mid-Career 90th Percentile Salary</th>\n",
              "      <th>Group</th>\n",
              "    </tr>\n",
              "  </thead>\n",
              "  <tbody>\n",
              "    <tr>\n",
              "      <th>0</th>\n",
              "      <td>Accounting</td>\n",
              "      <td>109800.0</td>\n",
              "      <td>46000.0</td>\n",
              "      <td>77100.0</td>\n",
              "      <td>42200.0</td>\n",
              "      <td>152000.0</td>\n",
              "      <td>Business</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>1</th>\n",
              "      <td>Aerospace Engineering</td>\n",
              "      <td>96700.0</td>\n",
              "      <td>57700.0</td>\n",
              "      <td>101000.0</td>\n",
              "      <td>64300.0</td>\n",
              "      <td>161000.0</td>\n",
              "      <td>STEM</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>2</th>\n",
              "      <td>Agriculture</td>\n",
              "      <td>113700.0</td>\n",
              "      <td>42600.0</td>\n",
              "      <td>71900.0</td>\n",
              "      <td>36300.0</td>\n",
              "      <td>150000.0</td>\n",
              "      <td>Business</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>3</th>\n",
              "      <td>Anthropology</td>\n",
              "      <td>104200.0</td>\n",
              "      <td>36800.0</td>\n",
              "      <td>61500.0</td>\n",
              "      <td>33800.0</td>\n",
              "      <td>138000.0</td>\n",
              "      <td>HASS</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>4</th>\n",
              "      <td>Architecture</td>\n",
              "      <td>85400.0</td>\n",
              "      <td>41600.0</td>\n",
              "      <td>76800.0</td>\n",
              "      <td>50600.0</td>\n",
              "      <td>136000.0</td>\n",
              "      <td>Business</td>\n",
              "    </tr>\n",
              "  </tbody>\n",
              "</table>\n",
              "</div>"
            ],
            "text/plain": [
              "     Undergraduate Major    Spread  ...  Mid-Career 90th Percentile Salary     Group\n",
              "0             Accounting  109800.0  ...                           152000.0  Business\n",
              "1  Aerospace Engineering   96700.0  ...                           161000.0      STEM\n",
              "2            Agriculture  113700.0  ...                           150000.0  Business\n",
              "3           Anthropology  104200.0  ...                           138000.0      HASS\n",
              "4           Architecture   85400.0  ...                           136000.0  Business\n",
              "\n",
              "[5 rows x 7 columns]"
            ]
          },
          "metadata": {
            "tags": []
          },
          "execution_count": 18
        }
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "uBokcGx_uj6R",
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 202
        },
        "outputId": "8449be8f-8d34-49a1-add0-a55d2b0bb050"
      },
      "source": [
        "low_risk = clean_df.sort_values('Spread')\n",
        "low_risk[['Undergraduate Major', 'Spread']].head()"
      ],
      "execution_count": null,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/html": [
              "<div>\n",
              "<style scoped>\n",
              "    .dataframe tbody tr th:only-of-type {\n",
              "        vertical-align: middle;\n",
              "    }\n",
              "\n",
              "    .dataframe tbody tr th {\n",
              "        vertical-align: top;\n",
              "    }\n",
              "\n",
              "    .dataframe thead th {\n",
              "        text-align: right;\n",
              "    }\n",
              "</style>\n",
              "<table border=\"1\" class=\"dataframe\">\n",
              "  <thead>\n",
              "    <tr style=\"text-align: right;\">\n",
              "      <th></th>\n",
              "      <th>Undergraduate Major</th>\n",
              "      <th>Spread</th>\n",
              "    </tr>\n",
              "  </thead>\n",
              "  <tbody>\n",
              "    <tr>\n",
              "      <th>40</th>\n",
              "      <td>Nursing</td>\n",
              "      <td>50700.0</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>43</th>\n",
              "      <td>Physician Assistant</td>\n",
              "      <td>57600.0</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>41</th>\n",
              "      <td>Nutrition</td>\n",
              "      <td>65300.0</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>49</th>\n",
              "      <td>Spanish</td>\n",
              "      <td>65400.0</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>27</th>\n",
              "      <td>Health Care Administration</td>\n",
              "      <td>66400.0</td>\n",
              "    </tr>\n",
              "  </tbody>\n",
              "</table>\n",
              "</div>"
            ],
            "text/plain": [
              "           Undergraduate Major   Spread\n",
              "40                     Nursing  50700.0\n",
              "43         Physician Assistant  57600.0\n",
              "41                   Nutrition  65300.0\n",
              "49                     Spanish  65400.0\n",
              "27  Health Care Administration  66400.0"
            ]
          },
          "metadata": {
            "tags": []
          },
          "execution_count": 19
        }
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "hQBSdbJIWqJY"
      },
      "source": [
        "# Solution: Degrees with the Highest Potential"
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "SShtBkCQKk3O",
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 202
        },
        "outputId": "1c26b91b-f17f-41ca-f7d6-32f3fa6d138a"
      },
      "source": [
        "highest_potential = clean_df.sort_values('Mid-Career 90th Percentile Salary', ascending=False)\n",
        "highest_potential[['Undergraduate Major', 'Mid-Career 90th Percentile Salary']].head()"
      ],
      "execution_count": null,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/html": [
              "<div>\n",
              "<style scoped>\n",
              "    .dataframe tbody tr th:only-of-type {\n",
              "        vertical-align: middle;\n",
              "    }\n",
              "\n",
              "    .dataframe tbody tr th {\n",
              "        vertical-align: top;\n",
              "    }\n",
              "\n",
              "    .dataframe thead th {\n",
              "        text-align: right;\n",
              "    }\n",
              "</style>\n",
              "<table border=\"1\" class=\"dataframe\">\n",
              "  <thead>\n",
              "    <tr style=\"text-align: right;\">\n",
              "      <th></th>\n",
              "      <th>Undergraduate Major</th>\n",
              "      <th>Mid-Career 90th Percentile Salary</th>\n",
              "    </tr>\n",
              "  </thead>\n",
              "  <tbody>\n",
              "    <tr>\n",
              "      <th>17</th>\n",
              "      <td>Economics</td>\n",
              "      <td>210000.0</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>22</th>\n",
              "      <td>Finance</td>\n",
              "      <td>195000.0</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>8</th>\n",
              "      <td>Chemical Engineering</td>\n",
              "      <td>194000.0</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>37</th>\n",
              "      <td>Math</td>\n",
              "      <td>183000.0</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>44</th>\n",
              "      <td>Physics</td>\n",
              "      <td>178000.0</td>\n",
              "    </tr>\n",
              "  </tbody>\n",
              "</table>\n",
              "</div>"
            ],
            "text/plain": [
              "     Undergraduate Major  Mid-Career 90th Percentile Salary\n",
              "17             Economics                           210000.0\n",
              "22               Finance                           195000.0\n",
              "8   Chemical Engineering                           194000.0\n",
              "37                  Math                           183000.0\n",
              "44               Physics                           178000.0"
            ]
          },
          "metadata": {
            "tags": []
          },
          "execution_count": 20
        }
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "C1hg41AqOkk3",
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 202
        },
        "outputId": "533f4ae0-ec05-4814-b9d6-ac94c870f9fa"
      },
      "source": [
        "highest_spread = clean_df.sort_values('Spread', ascending=False)\n",
        "highest_spread[['Undergraduate Major', 'Spread']].head()"
      ],
      "execution_count": null,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/html": [
              "<div>\n",
              "<style scoped>\n",
              "    .dataframe tbody tr th:only-of-type {\n",
              "        vertical-align: middle;\n",
              "    }\n",
              "\n",
              "    .dataframe tbody tr th {\n",
              "        vertical-align: top;\n",
              "    }\n",
              "\n",
              "    .dataframe thead th {\n",
              "        text-align: right;\n",
              "    }\n",
              "</style>\n",
              "<table border=\"1\" class=\"dataframe\">\n",
              "  <thead>\n",
              "    <tr style=\"text-align: right;\">\n",
              "      <th></th>\n",
              "      <th>Undergraduate Major</th>\n",
              "      <th>Spread</th>\n",
              "    </tr>\n",
              "  </thead>\n",
              "  <tbody>\n",
              "    <tr>\n",
              "      <th>17</th>\n",
              "      <td>Economics</td>\n",
              "      <td>159400.0</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>22</th>\n",
              "      <td>Finance</td>\n",
              "      <td>147800.0</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>37</th>\n",
              "      <td>Math</td>\n",
              "      <td>137800.0</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>36</th>\n",
              "      <td>Marketing</td>\n",
              "      <td>132900.0</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>42</th>\n",
              "      <td>Philosophy</td>\n",
              "      <td>132500.0</td>\n",
              "    </tr>\n",
              "  </tbody>\n",
              "</table>\n",
              "</div>"
            ],
            "text/plain": [
              "   Undergraduate Major    Spread\n",
              "17           Economics  159400.0\n",
              "22             Finance  147800.0\n",
              "37                Math  137800.0\n",
              "36           Marketing  132900.0\n",
              "42          Philosophy  132500.0"
            ]
          },
          "metadata": {
            "tags": []
          },
          "execution_count": 21
        }
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "kKeiNcrzO-K5",
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 202
        },
        "outputId": "3aaf2680-7e13-4447-a23a-3743257e45a5"
      },
      "source": [
        "highest_spread = clean_df.sort_values('Mid-Career Median Salary', ascending=False)\n",
        "highest_spread[['Undergraduate Major', 'Mid-Career Median Salary']].head()"
      ],
      "execution_count": null,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/html": [
              "<div>\n",
              "<style scoped>\n",
              "    .dataframe tbody tr th:only-of-type {\n",
              "        vertical-align: middle;\n",
              "    }\n",
              "\n",
              "    .dataframe tbody tr th {\n",
              "        vertical-align: top;\n",
              "    }\n",
              "\n",
              "    .dataframe thead th {\n",
              "        text-align: right;\n",
              "    }\n",
              "</style>\n",
              "<table border=\"1\" class=\"dataframe\">\n",
              "  <thead>\n",
              "    <tr style=\"text-align: right;\">\n",
              "      <th></th>\n",
              "      <th>Undergraduate Major</th>\n",
              "      <th>Mid-Career Median Salary</th>\n",
              "    </tr>\n",
              "  </thead>\n",
              "  <tbody>\n",
              "    <tr>\n",
              "      <th>8</th>\n",
              "      <td>Chemical Engineering</td>\n",
              "      <td>107000.0</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>12</th>\n",
              "      <td>Computer Engineering</td>\n",
              "      <td>105000.0</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>19</th>\n",
              "      <td>Electrical Engineering</td>\n",
              "      <td>103000.0</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>1</th>\n",
              "      <td>Aerospace Engineering</td>\n",
              "      <td>101000.0</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>17</th>\n",
              "      <td>Economics</td>\n",
              "      <td>98600.0</td>\n",
              "    </tr>\n",
              "  </tbody>\n",
              "</table>\n",
              "</div>"
            ],
            "text/plain": [
              "       Undergraduate Major  Mid-Career Median Salary\n",
              "8     Chemical Engineering                  107000.0\n",
              "12    Computer Engineering                  105000.0\n",
              "19  Electrical Engineering                  103000.0\n",
              "1    Aerospace Engineering                  101000.0\n",
              "17               Economics                   98600.0"
            ]
          },
          "metadata": {
            "tags": []
          },
          "execution_count": 22
        }
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "xG7RuPajWwkN"
      },
      "source": [
        "# Grouping and Pivoting Data with Pandas"
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "LKAVOVJTP5iQ",
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 206
        },
        "outputId": "b9eb6c5a-9f04-49e3-e99d-9c425a97f05f"
      },
      "source": [
        "clean_df.groupby('Group').count()"
      ],
      "execution_count": null,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/html": [
              "<div>\n",
              "<style scoped>\n",
              "    .dataframe tbody tr th:only-of-type {\n",
              "        vertical-align: middle;\n",
              "    }\n",
              "\n",
              "    .dataframe tbody tr th {\n",
              "        vertical-align: top;\n",
              "    }\n",
              "\n",
              "    .dataframe thead th {\n",
              "        text-align: right;\n",
              "    }\n",
              "</style>\n",
              "<table border=\"1\" class=\"dataframe\">\n",
              "  <thead>\n",
              "    <tr style=\"text-align: right;\">\n",
              "      <th></th>\n",
              "      <th>Undergraduate Major</th>\n",
              "      <th>Spread</th>\n",
              "      <th>Starting Median Salary</th>\n",
              "      <th>Mid-Career Median Salary</th>\n",
              "      <th>Mid-Career 10th Percentile Salary</th>\n",
              "      <th>Mid-Career 90th Percentile Salary</th>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>Group</th>\n",
              "      <th></th>\n",
              "      <th></th>\n",
              "      <th></th>\n",
              "      <th></th>\n",
              "      <th></th>\n",
              "      <th></th>\n",
              "    </tr>\n",
              "  </thead>\n",
              "  <tbody>\n",
              "    <tr>\n",
              "      <th>Business</th>\n",
              "      <td>12</td>\n",
              "      <td>12</td>\n",
              "      <td>12</td>\n",
              "      <td>12</td>\n",
              "      <td>12</td>\n",
              "      <td>12</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>HASS</th>\n",
              "      <td>22</td>\n",
              "      <td>22</td>\n",
              "      <td>22</td>\n",
              "      <td>22</td>\n",
              "      <td>22</td>\n",
              "      <td>22</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>STEM</th>\n",
              "      <td>16</td>\n",
              "      <td>16</td>\n",
              "      <td>16</td>\n",
              "      <td>16</td>\n",
              "      <td>16</td>\n",
              "      <td>16</td>\n",
              "    </tr>\n",
              "  </tbody>\n",
              "</table>\n",
              "</div>"
            ],
            "text/plain": [
              "          Undergraduate Major  ...  Mid-Career 90th Percentile Salary\n",
              "Group                          ...                                   \n",
              "Business                   12  ...                                 12\n",
              "HASS                       22  ...                                 22\n",
              "STEM                       16  ...                                 16\n",
              "\n",
              "[3 rows x 6 columns]"
            ]
          },
          "metadata": {
            "tags": []
          },
          "execution_count": 23
        }
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "2PPBqgJbRR_a",
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 189
        },
        "outputId": "567a3587-fc1e-4374-95c0-e45f1fe0dc1b"
      },
      "source": [
        "pd.options.display.float_format = '{:,.2f}'.format\n",
        "clean_df.groupby('Group').mean()"
      ],
      "execution_count": null,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/html": [
              "<div>\n",
              "<style scoped>\n",
              "    .dataframe tbody tr th:only-of-type {\n",
              "        vertical-align: middle;\n",
              "    }\n",
              "\n",
              "    .dataframe tbody tr th {\n",
              "        vertical-align: top;\n",
              "    }\n",
              "\n",
              "    .dataframe thead th {\n",
              "        text-align: right;\n",
              "    }\n",
              "</style>\n",
              "<table border=\"1\" class=\"dataframe\">\n",
              "  <thead>\n",
              "    <tr style=\"text-align: right;\">\n",
              "      <th></th>\n",
              "      <th>Spread</th>\n",
              "      <th>Starting Median Salary</th>\n",
              "      <th>Mid-Career Median Salary</th>\n",
              "      <th>Mid-Career 10th Percentile Salary</th>\n",
              "      <th>Mid-Career 90th Percentile Salary</th>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>Group</th>\n",
              "      <th></th>\n",
              "      <th></th>\n",
              "      <th></th>\n",
              "      <th></th>\n",
              "      <th></th>\n",
              "    </tr>\n",
              "  </thead>\n",
              "  <tbody>\n",
              "    <tr>\n",
              "      <th>Business</th>\n",
              "      <td>103,958.33</td>\n",
              "      <td>44,633.33</td>\n",
              "      <td>75,083.33</td>\n",
              "      <td>43,566.67</td>\n",
              "      <td>147,525.00</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>HASS</th>\n",
              "      <td>95,218.18</td>\n",
              "      <td>37,186.36</td>\n",
              "      <td>62,968.18</td>\n",
              "      <td>34,145.45</td>\n",
              "      <td>129,363.64</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>STEM</th>\n",
              "      <td>101,600.00</td>\n",
              "      <td>53,862.50</td>\n",
              "      <td>90,812.50</td>\n",
              "      <td>56,025.00</td>\n",
              "      <td>157,625.00</td>\n",
              "    </tr>\n",
              "  </tbody>\n",
              "</table>\n",
              "</div>"
            ],
            "text/plain": [
              "             Spread  ...  Mid-Career 90th Percentile Salary\n",
              "Group                ...                                   \n",
              "Business 103,958.33  ...                         147,525.00\n",
              "HASS      95,218.18  ...                         129,363.64\n",
              "STEM     101,600.00  ...                         157,625.00\n",
              "\n",
              "[3 rows x 5 columns]"
            ]
          },
          "metadata": {
            "tags": []
          },
          "execution_count": 24
        }
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "jMkNL2nGR6ia"
      },
      "source": [],
      "execution_count": null,
      "outputs": []
    }
  ]
}
