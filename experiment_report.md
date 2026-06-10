# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** AI20K-XXXX
**Name:** Phung Kim Khang
**Date:** 10/06/2026

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200.0. | 9 | Du lieu da duoc validate nen chi con product hop le, category dung va price la so duong. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 2 | Agent bi anh huong boi outlier va du lieu rac, nen goi y mot san pham khong hop ly. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Agent tra loi sai khi dung Garbage Data vi du lieu dau vao co nhieu van de chat luong. File garbage co duplicate ID, sai kieu du lieu o cot price, gia tri null va dac biet la outlier rat lon nhu Nuclear Reactor gia 999999 trong category electronics. Agent simulation chi loc theo category va chon record co price cao nhat, nen neu du lieu khong duoc validate thi no se xem outlier nay la lua chon tot nhat. Dieu nay cho thay prompt tot van khong du neu knowledge base bi nhiem du lieu rac. Pipeline can validation, type checking va outlier handling truoc khi dua du lieu cho agent.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Dong y.

Chat luong du lieu anh huong truc tiep den cau tra loi cua agent. Neu data co loi, agent co the dua ra cau tra loi tu tin nhung sai. Vi vay ETL pipeline va data observability la buoc quan trong truoc khi xay dung ung dung AI.
