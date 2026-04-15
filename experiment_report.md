# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** AI20K-202600164
**Name:** Nguyen Hoang Viet Hung
**Date:** 2026-04-15

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200.0. | 9 | Du lieu sach, cot price hop le, category nhat quan, ket qua dang tin cay. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 2 | Outlier gia qua lon + noise data lam agent uu tien item phi thuc te. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Trong bo garbage data, co nhieu van de chat luong du lieu cung luc xuat hien.
Thu nhat la duplicate id (id=1 xuat hien 2 lan) gay nham lan khi tong hop thong tin.
Thu hai la sai kieu du lieu, vi du gia "ten dollars" khong the chuyen thanh so,
lam giam do tin cay cua qua trinh truy van theo price. Thu ba la outlier rat lon
(Nuclear Reactor gia 999999) lam logic "chon gia cao nhat" bi lech hoan toan khoi
ngu canh business thong thuong. Thu tu la record rong category va price=0 the hien
du lieu khong day du. Khi khong co lop validation/manh loc du lieu, agent se hoc
tu thong tin ban va tao ra cau tra loi nghe co ve hop ly, nhung thuc te la sai muc tieu.
Vi vay, do chinh xac cua agent phu thuoc rat manh vao chat luong data dau vao.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** (Dong y hay khong? Giai thich ngan gon.)

Dong y. Prompt tot giup agent dien dat ro hon, nhung neu du lieu dau vao ban, sai,
hoac bi poison thi agent van co the dua ra ket luan sai. Trong bai test nay, cung mot
prompt nhung clean data cho ket qua dung hon rat nhieu so voi garbage data.
