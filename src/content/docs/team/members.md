---
title: Team Members & Roles
description: Invite your team, control who can access releases, financials, and marketing, and limit collaborators to specific artists.
---

ReleaseLoop is built for teams. Invite your A&R, marketing, publicists, and management staff into your workspace so everyone works from the same release schedule and artist roster.

![Settings team members page showing member list and roles](../../../assets/screenshots/settings-team.png)

## Inviting team members

Only the workspace owner sees **Invite Member**.

1. Go to **Settings**, then the **Team** tab
2. Click **Invite Member**
3. Enter their email address
4. Select their **Role** (Admin, A&R, Marketing, or Member)
5. Set their **Access** to **Entire workspace** or **Specific artists** (see [Artist access](#artist-access) below)
6. They receive an invitation. If they do not already have an account, the dialog says they will receive an invite link

Pending invitations have **Copy invite link**. The link looks like `https://app.releaseloop.com/join/` followed by a token.

## Roles

Each team member is assigned a role that controls what they can see and do. This lets you give your A&R team access to releases without them seeing financials, or let your publicist manage marketing activities without touching release metadata.

| Role | What they can do |
|------|-----------------|
| **Owner** | The person who owns the workspace. Only the owner can open Billing, invite people, change roles, and edit Role Permissions. |
| **Admin** | Full access to financials, contacts, and marketing, the same as the owner for those areas. The invite button and the Billing page stay with the owner. |
| **A&R** | A role the owner can limit. New workspaces start with contacts and marketing on, and financials off. |
| **Marketing** | Same starting access as A&R: contacts and marketing on, financials off. |
| **Member** | Same starting access as A&R: contacts and marketing on, financials off. |

The **Role Permissions** card is on **Settings**, then **Team**. It says owners and admins always have full access. The owner can turn **Financials & Royalties**, **Contacts**, and **Marketing** on or off for A&R, Marketing, and Member. Artist-scoped members do not see contacts or financials even if the role checkbox is on.

## Artist access

Role controls _what_ a member can do. **Access** controls _which artists_ they can see. The two are set independently, so you can give someone a powerful role over a narrow slice of your roster.

Every member or invitation has one of two access scopes:

| Access | What they see |
|--------|---------------|
| **Entire workspace** | The full artist roster and every release, contact, and financial in the workspace (subject to their role). |
| **Specific artists** | Only the artists you assign them, plus the releases and related data attached to those artists. The rest of your roster is hidden. |

When you choose **Specific artists** during invite (or when editing a member), an **Artists** picker appears -- select one or more artists to grant access to. Artist-limited members see a trimmed sidebar, artist list, and search, scoped to just their assigned artists.

This is built for collaborators you do not want to expose to the whole catalogue: a tour manager or day-to-day manager for one act, a freelance publicist working a single campaign, or an A&R contact tied to one signing. Access is enforced on the server, not just hidden in the interface.

The workspace owner can change a member's access at any time from **Settings**, then **Team**. Switch between Entire workspace and Specific artists, or adjust which artists are assigned.

## Managing members

From **Settings**, then **Team**, the workspace owner can:

- View all current members, their roles, and their artist access
- Change a member's role -- e.g., promote someone from Member to A&R as they take on more responsibility
- Change a member's access -- switch between Entire workspace and Specific artists, or update assigned artists
- Remove a member from the workspace -- they immediately lose access to all data
- See pending invitations
- Revoke unaccepted invitations

## Seat limits

Each lifetime seat ($49, one time) is one team member. The workspace can have as many members as the seats you have bought. Workspaces on the [older tiered plans](/billing/plans/#older-tiered-lifetime-plans) include a fixed number of seats:

| Plan | Seats |
|------|-------|
| **Lifetime seats** | As many as you buy |
| **Solo Lifetime** | 1 |
| **Label Lifetime** | 3 |
| **Agency / Pro Lifetime** | 10 |

When every seat is in use, **Invite Member** stays visible to the owner but shows **Team Member Limit Reached**, with a link to **Add more seats** on Billing. See [Plans & Pricing](/billing/plans/).

## Joining via invitation

When someone receives an invite:

1. They click the link in the invitation email (or the shareable link)
2. If they do not have a ReleaseLoop account, they create one
3. They are added to the workspace with the assigned role
4. The workspace appears in their workspace switcher -- they can start working immediately
