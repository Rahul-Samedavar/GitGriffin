# Git Griffin

Git Griffin is a **customtkinter** application designed to **moderate GitHub comments** efficiently. It leverages **machine learning** to detect spam comments across repositories, providing users with fine-tuned control over their moderation preferences.

---

## 🚀 Features

* **GitHub OAuth Integration**: Secure login using GitHub OAuth, ensuring that authentication tokens are stored only on the client-side database.
* **Spam Detection**: Trained a **Multinomial Naive Bayes Model** on over **100,000+ comments** for precise spam filtering.
* **Repository Selection**: Users can select repositories where moderation is applied.
* **Section-Specific Moderation**: Choose to moderate **Discussions, Issues, and Pull Requests**.
* **Action Preferences**: Decide whether to **hide spam comments** or **delete them permanently**.
* **Advanced Moderation Options**:

  * Remove entire **Discussions, Issues, or Pull Requests** if they are identified as spam.
  * Block or unblock spammers directly from the interface.
* **Fine-Tuning Support**:

  * The model adapts based on user corrections.
  * If a previously hidden comment is unhidden → **False Positive**.
  * If a comment is hidden by the user but not detected by the model → **False Negative**.
  * These examples are used to **incrementally fine-tune** the model, aligning it with individual user preferences.
* **Multi-threaded Execution**: Real-time moderation with a progress pop-up displaying detected spam messages.
* **Detailed Statistics**:

  * **Spam percentage** across the repository.
  * **Top spammers** with their spam count.
  * **Graphical representation** of spam trends.
* **GraphQL Integration**: Efficient querying and mutation operations via **GitHub GraphQL API** for seamless performance.

---

## 🛠 Installation & Setup

### Prerequisites

Ensure you have the following installed on your system:

* Python 3.8+
* pip
* GitHub account

### Clone the Repository

```sh
git clone https://github.com/Rahul-Samedavar/Git-Griffin.git
cd Git-Griffin
```

### Install Dependencies

```sh
pip install -r requirements.txt
```

### Environment Setup

Configure **OAuth credentials** by creating a `keys.py` file in the project root and adding:

```python
CLIENT_ID = '****************'
CLIENT_SECRET = '**************************'
```

[Learn more about generating GitHub OAuth credentials](https://docs.github.com/en/developers/apps/building-oauth-apps/creating-an-oauth-app)

### Running the Application

```sh
python app.py
```

---

## 🎯 Usage Guide

1. **Login with GitHub**

   * Click on the **Login** button.
   * Authenticate via **GitHub OAuth**.
   * Alternatively, paste your **GitHub Personal Access Token** and **Username** manually.
   * [Learn how to generate a GitHub token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)
   * Token is stored locally for security.

2. **Select Repository**

   * Choose the GitHub repository for moderation.

3. **Configure Moderation Settings**

   * Select sections: **Discussions, Issues, Pull Requests**.
   * Choose whether to **hide or delete spam comments**.
   * Optionally **delete entire spam-marked discussions/issues/PRs**.

4. **Start Moderation**

   * Click **Run Moderation**.
   * A real-time pop-up shows **progress** and **spam detection logs**.

5. **Review Statistics**

   * View **spam trends, percentages, and top spammers**.
   * Block/unblock spammers directly from the UI.

6. **Fine-Tune the Model**

   * If you **unhide** a comment marked as spam → it's logged as a **False Positive**.
   * If you **manually hide** a comment the model missed → it's logged as a **False Negative**.
   * Git Griffin uses these corrections to **fine-tune the spam detection model** and improve its future accuracy **specifically for you**.

---

## 🔍 Under the Hood

* **Machine Learning Model**:

  * Utilizes **Multinomial Naive Bayes** trained on **1L+ GitHub comments**.
  * Classifies comments as **spam or non-spam**.
  * Supports **personalized fine-tuning** based on user correction feedback.

* **Multi-threaded Execution**:

  * Ensures smooth, real-time moderation without UI freezes.

* **Database**:

  * Stores authentication tokens **securely on the client-side only**.
  * Tracks **spam statistics, moderation history, and user correction logs** for fine-tuning.

* **GraphQL API**:

  * Performs **efficient data retrieval and mutation** for GitHub repositories.

---

## 📜 License

This project is licensed under the **MIT License**. See `LICENSE` for details.

---

## 🤝 Contributing

We welcome contributions! Follow these steps:

1. Fork the repository.
2. Create a feature branch (`git checkout -b feature-name`).
3. Commit changes (`git commit -m 'Add feature'`).
4. Push to the branch (`git push origin feature-name`).
5. Open a pull request.

---

Enjoy **Git Griffin** and keep your GitHub repositories **spam-free and smartly adaptive**! 🦅🚀
